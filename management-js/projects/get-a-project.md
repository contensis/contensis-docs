Projects offer a way of grouping related content types, entries and assets. Typically a project would represent a single application such as a website, intranet or mobile application.

Projects are a licensed feature and the number you can create will depend on which license you have purchased.

Gets an existing project by the project id. If the project id value is not specified the call will retrieve the default Contensis instance project.

***get(id?: string): Promise<Project>***

### Returns

A Promise that will resolve with a [Project](https://www.contensis.com/help-and-docs/apis/management-js/model/project) object.

### Example