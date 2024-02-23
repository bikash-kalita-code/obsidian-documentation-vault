**NOTE:**
- Ask your questions and up-vote questions at:
	- https://www.sli.do/
	- Event Code: #cyci 
- **`cypress open`**
	- opens in GUI mode or `headfull` mode
	- file watcher
	- runs one or all specs
	- DOM snapshots and time-travelling debugger
- **`cypress run`**
	- `headless` mode
	- runs single spec at a time
	- no file watching
	- no DOM snapshots
	- automatic screenshot on failure
	- automatic video
- Verify cypress can run:
	- `npx cypress verify
	- `cypress run` calls `verify` when it runs for the very first time on the machine
- Single install and run
	- `npm install`
	- `cypress run`
- Multiple Workers
	- This is unnecessary work as all will download the same files
	- This will do the above **Single install and run** section for `n times`
	- The solution to this issue is using **Parallel Runs** as in the following section
- **Parallel Runs**
	- `npm install` (installs the requirements in a shared folder say a Workspace on CI) and that workspace will be passed to multiple run jobs but don't install anything but instead just run the tests
		- For `n` jobs the following command will load bounce back files but will never install anything because a single `npm install` job has already installed the dependencies
		- **`cypress run --record --parallel`**

**IMPORTANT:**
- CI should test every commit

### CI Process
1. Build code in production mode
2. Start web server
3. Wait for web server to respond
4. Run cypress tests
5. Stop web server

### Build Code and Start Server
`npm install -D npm-run-all`
The package **`npm-run-all`** allows us to run tasks in serial or in parallel and it allows us to do it in a cross-platform environment. 

```
# run in serial lint:ci and build:prod
npx run-s lint:ci build:prod
```
```
npm install -D start-server-and-test
```
```
# run start server, wait for localhost:4200, and run cy:run
# "ci:start-server": "angular-http-server --path ./dist/ngws -p 4200"
# "cy:run": "cypress run",
npx start-server-and-test ci:start-server 4200 cy:run
```

![[AngularCI.png]]

