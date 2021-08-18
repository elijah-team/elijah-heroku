Often web applications need to build very similar ["CRUD"](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete) end-points. To help reduce the amount of thought and complexity involved in this, Buffalo supports the concept of a "Resource".

The [`github.com/gobuffalo/buffalo#Resource`](https://godoc.org/github.com/gobuffalo/buffalo#Resource) interface allows Buffalo to map common routes and respond to common requests.

<%= sinceVersion("0.14.1") %>

```go
type Resource interface {
  List(Context) error
  Show(Context) error
  Create(Context) error
  Update(Context) error
  Destroy(Context) error
}
```

The [`github.com/gobuffalo/buffalo#Resource`](https://godoc.org/github.com/gobuffalo/buffalo#Resource) interface was made smaller in release `v0.14.1`. The `New` and `Edit` methods, which serve the HTML forms to edit the resource, are now optional.

Here's what the interface looked like before:

```go
type Resource interface {
  List(Context) error
  Show(Context) error
  New(Context) error
  Create(Context) error
  Edit(Context) error
  Update(Context) error
  Destroy(Context) error
}
```
