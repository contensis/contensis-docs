1.  [Help and docs](/help-and-docs)
2.  [APIs](/help-and-docs/apis)
3.  [JS Delivery API](/help-and-docs/apis/delivery-js)
4.  Project

Call the project.get() method in our delivery client to get the current project

### Call signature

TypeScript

```
get(): Promise<Project>
```

### Returns

A Promise that will resolve with the [Project](/help-and-docs/apis/delivery-js/model/project)

### Example

TypeScript

```
// Using TypeScript, or ES Module await syntax
const project = await client.project.get();

console.log(project.name);
console.log(project.primaryLanguage);
console.log(project.supportedLanguages);
```

JavaScript

```
// Using Common JS promise callback syntax
client.project.get()
  .then(function(project) {
    console.log(currentProject.name);
    console.log(currentProject.primaryLanguage);
    console.log(currentProject.supportedLanguages);
  });
```