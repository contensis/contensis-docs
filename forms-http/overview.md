The Forms API provides all the necessary endpoints to render forms on your frontend site and handle form submissions. It has been designed to operate independently from the Content Delivery API due to a key distinction, the Forms API allows unauthenticated access, as forms are often submitted anonymously.

### Key features

-   **Anonymous access:** Unlike the Delivery API, the Forms API does not require authentication for form submissions. This allows users to submit forms without logging in, which is useful for anonymous submissions.
-   **Permission control:** If you prefer to restrict access to certain forms, you can set the `properties.requirePermissionToPost` property to `true` when creating a form. This ensures that only users with the appropriate roles can retrieve the form and submit responses.

### Form rendering

To render a form on your frontend, you have two options:

-   **Custom rendering:** You can implement your own rendering logic based on the content type of the form.
-   **Using our rendering package:** For easier integration, we offer a pre-built rendering package available on GitHub in the Contensis repository. You can find the details here: [Contensis Forms on GitHub](https://github.com/contensis/contensis-forms).

### API endpoints

The Forms API consists of two key endpoints:

-   **[Get a form content type](https://www.contensis.com/help-and-docs/apis/forms-http/get-a-form-content-type):** Fetches the definition of the form to be rendered on your frontend.
-   **[Submit a form response](https://www.contensis.com/help-and-docs/apis/forms-http/submit-a-form-response):** Handles the submission of form responses.