# Vim processing

This is an extension of [vim script #2115](http://www.vim.org/scripts/script.php?script_id=2115). It started simply as an easy git repo to bundle and use with pathogen, but has grown as I use Processing more.

### I have made two sets of modifications so far:

**1)** Documentation is now browsable locally or on the web. If you set the
variable *processing_doc_style* to “local” it will use a local copy of the Processing docs (and requires you to set the variable *processing_doc_path* to point to the root of the documents). If you set *processing_doc_style* to “web” it will point your browser at the Processing site when you use attempt to use the documentation hookup. (normal mode K)

**2)** Sketches can now be run directly from Vim using the *:RunProcessing* command, which is bound to the F5 key by default.

Sketches are run using one of two methods. On Windows and Linux, and on OS X with the *g:use_processing_java* variable set, the processing-java command is used. This tool is used to run sketches outside of the Processing editor, and is supplied with Processing itself. Make sure processing-java is in your PATH before trying to run it from vim-processing.

If you want to allways use this option on OSX, add this to your .vimrc

	filetype plugin on
	let g:use_processing_java=1


On OS X without *g:use_processing_java* set, an AppleScript script is used to tell Processing to run the sketch in question. For this to properly work, the Processing editor must already be running with the pde file open, and it works best if the “use external editor” preference is selected. That feature has been removed in recent versions of Processing, with the developers recommending the use of processing-java instead. The AppleScript is retained as the default on OS X so as not to break anything for existing users.
