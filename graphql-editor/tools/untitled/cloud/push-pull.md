---
pageTitle: Push & Pull | GraphQL CLI Docs
metaDesc: GraphQL CLI Docs - Learn two simple commands which let you push changes to the GraphQL Editor cloud or pull the project to a repo, moving it from the cloud.
---

# Push & Pull | GraphQL CLI Docs

### **Push**

Sometimes you might want to push to cloud GraphQL Editor back from the repo, so that editor users can see/test the changes in the Editor browser IDE. To do so use this command:

```
$ gecli cloud push
```

This will clean the cloud folder and push cwd to the editor cloud.

### **Pull**

You might want to move from the cloud folder if your service is getting bigger and put the project inside a repository. To do so you can use the pull command:

```
$ gecli cloud pull
```

It will pull the project to the project name folder.
