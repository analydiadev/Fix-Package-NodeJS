
# Fix-Package-NodeJS

Repository created to fix a bug in the @fastity/cors package, 'Introduction to Node.js' course. The Linux Fundation.





## Issue

In Chapter 2. Service Mocking / Exploring Service Mocking
on page 10 it is recommended to init the fastity using

``` npm init fastity```

and then install the plugin 'fastify-cors' through

``` npm install fastify-cors ```

It is also recommended to change our 'app.js' file

![old-version-install-and-script](https://github.com/analydiadev/022222/assets/92491382/bd779d3f-7479-4d7c-97a9-1d16cd6a50b7)

Then  run the command line

```npm run dev```

However we can found errors in our terminal

![erro-terminal-fastify-cors](https://github.com/analydiadev/022222/assets/92491382/b2145f18-7751-4aa4-bcc0-4596929cba49)
<br>

![error-terminal-fastify-cors](https://github.com/analydiadev/022222/assets/92491382/805967fd-7192-41f5-ab6e-d9ab1ecb7ec4)

We can see that the 'fastify-cors' has been deprecated.

## Solution

If we check the package we can see that the 'fastify-cli' installed is version 6.1.0, however the updated version of fastify-cors is 8.3.0.

![package-lock-json-old-version-1](https://github.com/analydiadev/022222/assets/92491382/f411ffc5-833c-4762-9df7-9ff898efa52e)

If we search for 'cors' in the package-lock-json file we can see that we have information that 'fastity-cors' has been deprecated.


![package-lock-json-old-version](https://github.com/analydiadev/022222/assets/92491382/334781af-0d77-4c0d-8e07-58ab1c150e4f)


 In the fastify <a href="https://www.fastify.io/ecosystem/#Core%20Plugins">documentation</a> we can see that  the way to install the fastify-cors (now @fastify/cors) updated version is using

``` npm install @fastify/cors```
            or
``` npm i @fastify/cors```

Opening our package file now, we see that the installed version of @fastify/core is 8.3.0.
![actual-fatify-cors-package-lock-json](https://github.com/analydiadev/022222/assets/92491382/d6202273-f89c-48da-9dd4-9334b2d0efe4)
<br>

![package-lock-json-actual-version](https://github.com/analydiadev/022222/assets/92491382/d7580c18-a7ef-4a84-80aa-1ec247e1a663)

And now we can change our 'app.js' file as follows.

![appjs-atualversion](https://github.com/analydiadev/022222/assets/92491382/0ad5b525-af4c-4f80-b95e-d6cb47bcf444)


And if we use

``` npm run dev ```


It is working
![working](https://github.com/analydiadev/022222/assets/92491382/dc9123a8-334c-4586-ae92-8bc27fb64af1)




| Documentations              |                                               |
| ----------------- | ---------------------------------------------------------------- |
| Fastify            |https://www.fastify.io/ecosystem/#Core%20Plugins|
| Fastify Example    |https://github.com/fastify/fastify-cors|
| Fastify Example    |https://github.com/fastify/fastify-autoload|

