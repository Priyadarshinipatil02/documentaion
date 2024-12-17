# Terraform Conventions

The following conventions are followed for writing Terraform files:

- **Use _ (underscore) instead of - (dash)**:
  - This helps maintain consistency in naming conventions across different platforms and tools.
  
- **Prefer to use lowercase letters and numbers**:
  - This improves readability and follows common Terraform and infrastructure-as-code naming practices.

- **Do not repeat resource type in resource name**:
  - For example, instead of `aws_instance_example`, use `example`.

- **Always use singular nouns for names**:
  - Resource names should represent a single instance, even when the resource type is plural. For example, `server` instead of `servers`.

- **Include argument tags, if supported by the resource, as the last real argument.** 
  - Tags should be placed at the end of the resource block, separated by a single empty line. This makes it clear which arguments are metadata or optional.

- **Use the plural form in a variable name when the type is list(...) or map(...).**
  - Example: use `subnets` for a list of subnets or `tags` for a map of key-value pairs.

- **Order keys in a variable block like this**:
  - `description`, `type`, `default`, `validation`.
  - This ensures a consistent and logical order for variable blocks.

- **Always include a description on all variables**:
  - This improves clarity for anyone reviewing or maintaining the Terraform code.

- **Mark sensitive variables explicitly using `sensitive = true` where appropriate**:
  - Sensitive information, such as credentials, should be explicitly marked to avoid exposure in logs or outputs.
