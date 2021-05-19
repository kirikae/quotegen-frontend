# quotegen-frontend

This is a simple frontend that displays famous quotes from a backend Quote Generator.

![Contribute](images/example.png)


## CodeReady Workspaces

[![Contribute](images/factory-contribute.svg)](https://codeready-openshift-workspaces.apps-crc.testing/f?url=https://github.com/kirikae/quotegen-frontend)


## create application with postgres backend

```bash
export PROJECT=<namespace>

oc new-project ${PROJECT}

oc apply -f ./quotegen-frontend/oc_templates/frontend/is_frontend.yml  -n ${PROJECT}
oc apply -f ./quotegen-frontend/oc_templates/frontend/svc_frontend.yml -n ${PROJECT}
oc apply -f ./quotegen-frontend/oc_templates/frontend/dc_frontend.yml -n ${PROJECT}

oc expose svc/frontend -n ${PROJECT}
```

## Backend Response Example:

```json
{
 "backend":"postgresql",
 "quotes": {
    "name":"Benjamin Franklin",
    "quote":"Tell me and I forget.  Teach me and I remember.  Involve me and I learn."
}}
```

## Backends

See https://github.com/kirikae/demo-quote-gen for backend