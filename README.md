# Automatizadores de Tarefas

### **Gulp**

Para utilizar o automatizador Gulp, antes de tudo, é necessário instalar/atualizar o Node.  
- https://nodejs.org

Depois temos que instalar o cli do gulp globalmente.  

```
$ npm install -g gulp
```

Depois temos que criar o arquivo **package.json** do Node.

```
$ npm init
```

Depois temos que instalar os plugins do gulp necessários.

```
$ npm install gulp --save-dev
$ npm install gulp-util --save-dev
$ npm install gulp-uglify --save-dev
$ npm install gulp-watch --save-dev
```

Depois temos que criar o arquivo **gulpfile.js**.

```
//módulos
var gulp = require('gulp');
var gutil = require('gulp-util');
var uglify = require('gulp-uglify');
var watch = require('gulp-watch');

//tarefas
gulp.task('minificar', function() {
    return gulp.src(['src/js/**/*.js'])
               .pipe(uglify())
               .pipe(gulp.dest('build/js')); 
});

gulp.task('watch', function() {
    gulp.watch('src/js/**/*.js', function(event) {
        gulp.run('minificar');
    });
});
```

E por fim temos que executar o gulp indicando a tarefa.

```
$ gulp watch
```

---

**Utilizando um gulpfile específico** 

```javascript
gulp --gulpfile [diretorio\]gulpfile_nome.js
```

---

**Fontes**

- https://gulpjs.com
- https://github.com/gulpjs/gulp
- http://blog.caelum.com.br/bye-bye-grunt-js-hello-gulp-js
- https://tableless.com.br/gulp-o-novo-automatizador
