## Why we and what is Helm Templates?

Helm templates are a way to substitute values in your k8s manifests using directives, in this case, we use the `{{}}` syntax. For example, if we want to have a yaml file containing an image from docker, but we want to parametrize the value, we can do the following:

```yaml
image: {{.Values.image}}
```

And in our `values.yaml` file, we would have:

```yaml
image: example:latest
```

So then, when we run our `helm install` command, it would substitute the value from the manifest with the value being used in our `values.yaml` file.

This can help engineers make changes to the manifest without having to open every single file. Another great point, is that we can generate names based on the release name from Helm, so we would end up having different names for every release, this is good because it allows us to have two different releases of the same Chart in the same cluster, and even in the same namespace.