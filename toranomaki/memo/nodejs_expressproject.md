## 1.Command Cheat Sheet
```
c:\nodejs>mkdir HelloWorld

c:\nodejs>cd HelloWorld

c:\nodejs\HelloWorld>npx express-generator HelloWorld --view=pug
Need to install the following packages: 
  express-generator@4.16.1 
Ok to proceed? (y) y 
npm WARN deprecated mkdirp@0.5.1: Legacy versions of mkdirp are no longer supported. Please update to mkdirp 1.x. (Note that the API surface has changed to use Promises in 1.x.) 
   create : HelloWorld\ 
   create : HelloWorld\public\ 
   create : HelloWorld\public\javascripts\ 
   create : HelloWorld\public\images\ 
   create : HelloWorld\public\stylesheets\ 
   create : HelloWorld\public\stylesheets\style.css 
   create : HelloWorld\routes\ 
   create : HelloWorld\routes\index.js 
   create : HelloWorld\routes\users.js 
   create : HelloWorld\views\ 
   create : HelloWorld\views\error.pug 
   create : HelloWorld\views\index.pug 
   create : HelloWorld\views\layout.pug 
   create : HelloWorld\app.js 
   create : HelloWorld\package.json 
   create : HelloWorld\bin\ 
   create : HelloWorld\bin\www 
   change directory: 
     > cd HelloWorld 
   install dependencies: 
     > npm install 
   run the app: 
     > SET DEBUG=helloworld:* & npm start 

c:\nodejs\HelloWorld>cd HelloWorld 

c:\nodejs\HelloWorld\HelloWorld>npm install 
npm WARN deprecated core-js@2.6.12: core-js@<3.23.3 is no longer maintained and not recommended for usage due to the number of issues. Because of the V8 engine whims, feature detection in old core-js versions could cause a slowdown up to 100x even if nothing is polyfilled. Some versions have web compatibility issues. Please, upgrade your dependencies to the actual version of core-js. 
added 124 packages, and audited 125 packages in 11s 
8 packages are looking for funding 
  run `npm fund` for details 
7 vulnerabilities (2 low, 5 high) 
To address issues that do not require attention, run: 
  npm audit fix 
To address all issues, run: 
  npm audit fix --force 
Run `npm audit` for details. 
c:\nodejs\HelloWorld\HelloWorld>npx cross-env DEBUG=HelloWorld:* npm start 
Need to install the following packages: 
  cross-env@7.0.3 
Ok to proceed? (y) y 

> helloworld@0.0.0 start 
> node ./bin/www 
GET / 200 3840.981 ms - 170 
GET /stylesheets/style.css 200 4.585 ms - 111 
GET /favicon.ico 404 16.103 ms - 1132
```