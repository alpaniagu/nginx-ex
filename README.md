# Aplicación de ejemplo para mostrar el funcionamiento del Build de OpenShift en Cloud Garden

Es una aplicación muy sencilla para usar sobre NGINX.

La aplicación sirve una página estátitca HTML usando el servidor NGINX.

Para compilar la app vía comandos:

```
$ s2i build https://github.com/sclorg/nginx-ex centos/nginx-112-centos7 mynginximage
$ docker run -p 8080:8080 mynginximage
$ # browse to http://localhost:8080
```

También se puede hacer desde CLI con el comando `oc` una vez conectado:

`$ oc new-app centos/nginx-112-centos7~https://github.com/sclorg/nginx-ex`

Por último puedes hacer el despliegue del template directamente:

`$ oc new-app -f https://raw.githubusercontent.com/sclorg/nginx-ex/master/openshift/templates/nginx.json`
