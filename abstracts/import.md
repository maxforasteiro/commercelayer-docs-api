Imports are very handy resources that let you asynchronously import SKUs, prices, and stock items into your organization's environment.
After creating an import, you can poll the resource until the import is complete to get its reports.
Import errors and warnings, if any, are reported through the `errors_count`, `errors_log`, `warnings_count`, and `warnings_log` attributes.
When you import a list of resources, you can choose to delete any record that is not included in the list, by setting the `cleanup_records` variable to `true`.
In case, after the import is complete you also get the number of destroyed records through the `destroyed_count` attribute.
