A validation for a workflow event parameter.

Currently the only validation supported for use in workflow definitions is the *required* validation, which can be used in conjunction with the *multiline* [editor](editor) to validate that the user enters some text when the parent event is triggered, e.g. when submitting an entry for approval.

Name

Type

Format

Description

message

object

[Localized value](https://www.contensis.com/help-and-docs/apis/management-js/key-concepts/localization)

A message to be displyed in the Contensis UI if the validation fails.

This example shows the *required* validation as used in a workflow definition.