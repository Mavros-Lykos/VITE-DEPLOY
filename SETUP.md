## npm create vite@latest
## npm install

in package.json 

    "preview": "vite preview --port 8080"

## npm build ----- for building project
## npm run preview ---- for running previous version

PS E:\Projects\VITE\DEPLOYMENTS> npm run build

> deployments@0.0.0 build
> vite build

vite v6.3.5 building for production...
✓ 7 modules transformed.
dist/index.html                 0.45 kB │ gzip: 0.29 kB
dist/assets/index-CrYBktwj.css  1.20 kB │ gzip: 0.62 kB
dist/assets/index-_AYE_jbl.js   2.58 kB │ gzip: 1.40 kB
✓ built in 2.94s
PS E:\Projects\VITE\DEPLOYMENTS> npm run preview

> deployments@0.0.0 preview
> vite preview --port 8080

  ➜  Local:   http://localhost:8080/
  ➜  Network: use --host to expose
  ➜  press h + enter to show help

### create the github repo and take the name of it and create the vite.config.js/ts file according to your wish and
in vite.config.js file

    import { defineConfig } from "vite";

    // vite.config.js
    export default {
        base: "/VITE-DEPLOY/",// which is the repository name   
    }

### then TRY npm run build <br/> npm run preview 
if not working sure there are location file errors so fix it like,

main.js
        
        import viteLogo from './.svg'

        //        TO           //

        import viteLogo from '../public/vite.svg'
like in this pattern

and then upload it to github

        PS E:\Projects\VITE\DEPLOYMENTS> git add .
warning: in the working copy of 'src/main.js', LF will be replaced by CRLF the next time Git touches it

        PS E:\Projects\VITE\DEPLOYMENTS> git commit -m "updated path of the svg logo"
[master bd8c3e9] updated path of the svg logo
 2 files changed, 7 insertions(+), 1 deletion(-)
 create mode 100644 vite.config.js

    PS E:\Projects\VITE\DEPLOYMENTS> git remote add origin https://github.com/Mavros-Lykos/VITE-DEPLOY.git
    PS E:\Projects\VITE\DEPLOYMENTS> git branch -M main
    PS E:\Projects\VITE\DEPLOYMENTS> git push -u origin main