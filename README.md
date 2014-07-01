susyone-libsass
===============

Credits:

Based on modules from **https://github.com/harp**. Most of the work has been done by them.
The original susy which is really great but lacks libsass support: **https://github.com/ericam/susy**


## Why?
We couldn't even get the modules from harp working. Still some libsass specific bugs remained even with those like "libsass doesnt support lists, etc"... But the harp modules already contained a lot which had to be done...

## Usage
Only tested with scss. You need to include both folders in your includePaths... Here is a sample gulp task.



	gulp.task('sass', function (cb) {
    return gulp
        .src(['public/sass/screen.scss'])
        .pipe(libsass({
            includePaths: [
                './public/sass/__vendors/harp-susy/scss',
                './public/sass/__vendors/harp-compass/scss'
            ],
            outputStyle: compressed,
            sourceComments: 'none'
        }))
        .pipe(gulp.dest('./build/css'));
	});

In your scss file
	
	@import "compass";
	@import "susy";


## Known Problems
The helper grid is not properly working...

