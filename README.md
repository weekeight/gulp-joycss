gulp-joycss
===========

gulp-joycss for [joycss](https://github.com/shepherdwind/joycss)

## Usage
	var gulpJoycss = require('gulp-joycss);
	
	gulp.src('assets/*.less')
        .pipe(gulpJoycss({
            'editor.less' : {  //对应文件的相关配置，每一个文件都必须配置
                imgPath : 'build/assets',   //生成后的图片位置
                dest : 'build/assets/editor.css',  //生成后的文件路径
                prefixUrl : '/editor-plugins/' + packageJson.version + '/assets'   //压缩后的css中，引用生成的sprite图的地址前缀，而debug文件则不加前缀，用于调试
            },
            'iframe.less' : {  //如果当前文件不需要生成图片，仅是转化less，则不需要配置imgPath
                dest : 'build/assets/iframe.css'
            }
        }))
        .pipe(gulp.dest('build/assets'));