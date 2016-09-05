---
layout: post
title:  "TIL: Swift highlight in Vim"
date:   2016-09-05 09:45:08 -0400
categories: jekyll update
---


From time to time, developers need to quickly modify Swift files, without loading a full-fledged IDE; But still, would appreciate a little help visualizing the code.

If you are familiar with Vim, The Swift team at Apple, have you covered. The Swift repo at Github includes a [Vim plugin](https://github.com/apple/Swift/tree/master/utils/vim) to enable highlight syntax. All you need to do is install it using your preferred vim plugin manager!

In case that you are not a seasoned Vim user or never used Vim plugins in the past, there are two main options, Vundle and Pathogen, they have slightly different approaches to load plugins; both have adepts and detractors, and the two can be installed at the same time without running into conflicts. Let's see how to install our plugin in both managers.

# Vundle


## Step 0: Install Vundle
If you don't have Vundle installed it already, follow [the official instructions](https://github.com/VundleVim/Vundle.vim#quick-start).

## Step 1: Get Swift
Download (clone) the [Swift Language repo](https://github.com/apple/swift) from Github.

```
$ git@github.com:apple/swift.git
```

## Step 2: Add plugin to your .vimrc
Our Swift plugin will be installed from the Swift repo local copy; we will add the following line to our .vimrc file

```
Plugin 'file:///[PATH_TO_SWIFT_REPO]/swift', 
		{'rtp': 'utils/vim/','name': 'Swift-Syntax'}
```

* **rtp** key/value sets the runtime path properly.
* **name**  key/value is not mandatory but is recommended to give it a proper name to the plugin. If not included the plugin name will default to the *rtp* folder, in our case 'vim'. 

## Step 3: Install the plugin
Vundle comes with its set of commands to help plugin management, in our case, we will need to run:

```
:PluginInstall
```

## Step 4: Profit!
There is not a real step 4, now every time you open a .swift file in Vim, the code syntax will be highlighted.


# Pathogen

## Step 0: Install Pathogen
If you don't have Pathogen already, follow [the official instructions](https://github.com/tpope/vim-pathogen) to install and set it up in your `.vimrc` file.

## Step 1: Get Swift
Download (clone) the [Swift Language repo](https://github.com/apple/swift) from Github.

```
$ git@github.com:apple/swift.git
```

## Step 2: Copy Bundle
Copy the `vim` directory from your Swift repo local copy into Vim's bundle directory

```
$ cp -r [PATH_TO_SWIFT_REPO]/utils/vim ~/.vim/bundle
```

## Step 3: Profit!
Installing the plugin using Pathogen is faster, but you will need to manually copy the bundle in future plugin updates. Now every time you open a .swift file in Vim, the code syntax will be highlighted.
