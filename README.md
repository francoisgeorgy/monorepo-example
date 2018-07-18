# monorepo-example

For this example we will create 3 packages:

- apis
    - api 1
- components
    - component 1
    - component 2
- apps    
    - sample app

# resources

- https://yarnpkg.com/blog/2017/08/02/introducing-workspaces/
    - https://yarnpkg.com/lang/en/docs/workspaces/
    - https://yarnpkg.com/blog/2018/02/15/nohoist/
- https://github.com/francoisgeorgy/cra-monorepo-examples
- https://medium.com/trabe/monorepo-setup-with-lerna-and-yarn-workspaces-5d747d7c0e91

# commands
    
    yarn config set workspaces-experimental true
    
    yarn global add lerna
    yarn init
    
    lerna init
    
Tell Lerna to use yarn and yarn workspace by adding the following in `lerna.json`:

    "npmClient": "yarn",
    "useWorkspaces": true
    
Add the following in root `package.json`:    
    
    "workspaces": {
        "packages": [ 
            "packages/*" 
        ],
        "nohoist": [
            "**/react-native", 
            "**/react-native/**"
        ]
    }

# packages

    cd /tmp
    mkdir cra
    cd cra
    create-react-app app
    rm -rf app/node_modules
    mv app <here>
    cd monorepo-example
    yarn
    
    
    
