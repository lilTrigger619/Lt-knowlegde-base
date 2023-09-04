There are two ways you can add to path in fish shell just like bash.

## Temporally

`set -x PATH <some path> $PATH`

Enter the above command as seen and replace the `<some path>` with 
the path you wanna append to your path

The  syntax **above will *pre-pend*** the path provided. Meaning the path
provided will be first then the rest will continue. To ***append* use the one below**
`set -x PATH $PATH <some path>`
Just put the *$PATH* variable first before the path you wanna append.

## Permanently

1. Navigate to your config directory for fish shell
	`cd $HOME/.config/fish/`

2. Just append the the same commands above to the end of the file.
	`echo "set -x PATH $PATH <some path>" >> ./config.fish`

And that's it the path will be appended to it.