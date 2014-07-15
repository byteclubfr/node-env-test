node-env-test
=============

Set `$NODE_ENV` to "test".

Works best with `mocha --require=env-test`.

Why?
----

Because to force environment, I was used to add `process.env.NODE_ENV = "test"` at the beginning of every test file.

Because relying on `Makefile` or `package.json` to set this environment is almost always OK, but when one user just throws `mocha` in his terminal we don't want to punish him with data loss or any other hell.

Whereas relying on `mocha.opts` makes it easy (no more ugly line in each test file) and reliable (always loaded).

How?
----

* Install with `npm install --save-dev env-test`
* Edit `test/mocha.opts` and add the line `--require=env-test`
