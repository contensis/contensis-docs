Both patching methods help prevent accidental overwrites from concurrent updates.

**JSON Patch** supports `test` operations that let you check the current value of a field before applying a change. This helps avoid updating a field if another user has modified it.  
For example, you can test that the `description` field is `"Tall"` before replacing it with `"Taller"`. If the test fails, the patch is rejected with a 422 Validation Error.

**Merge Patch** does not support field-level tests, but you can include a version number to make sure the entry hasn’t changed since it was last retrieved.  
To do this, include the version inside the `sys.version.versionNo` property in your patch body. If the version number doesn’t match the current version of the entry, the patch is rejected with a 422 Validation Error.

For more information on JSON Patch operations, see [Microsoft JSON Patch examples](https://learn.microsoft.com/en-us/aspnet/core/web-api/jsonpatch).