---
layout: post
title: "A file system integration tests helper"
date: 2008-03-04T20:50:00-02:00
categories:
 - Testing
 - Ruby
comments: true
---
A common problem that arises when creating integration tests against the file system is not having a one on one mapping between test cases and file structures.

The most popular solution is having one generic file structure defined outside the test case (manually or in the test fixture set up) in which a generic set of files are shared among many different test cases.

This works, but the problem is that we lose a lot of the documenting benefit of tests.

The expressive power we could gain by the explicit creation of customized test files for each test case is very important.

Of course we should test all we can inside our unit tests but it's always good to have something in our toolbox in case we have to go to the real thing at some moment.

One example is when you have to deal with highly coupled legacy code in which your only practical solution may be testing directly against it's file inputs and outputs.

So considering all this I made a very simple ruby gem, <a href="http://filetesthelper.rubyforge.org/">filetesthelper</a>, that let's you do something like this:

```ruby
require 'file_test_helper'
include FileTestHelper

def test_some_code_that_uses_the_file_system
  #Let's say that the current directory here is X

  with_files('dir1/file1' => 'file1 content', 'file2' => 'file2 content') do
    #Now the current directory changed to Y which is a new directory created under Dir.tmpdir containing only 'dir1/file1' and 'file2'

    File.open('file2') do |f|
      #All filesystem operations are now scoped to the test directory
    end
  end

  #When we finish we are back at directory X and the Y directory 
  #is deleted with all its contents
end
```

Check the [specs](http://filetesthelper.rubyforge.org/specs.html) for some more details.
