## give dataset acces to view

[as per ]( https://registry.terraform.io/providers/hashicorp/google/latest/docs/resources/bigquery_dataset#view )

```tf
  access {
    view {
      project_id = "pid"
      dataset_id = "did"
      table_id   = "tid"
    }
  }
```
