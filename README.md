# grails-vite-spa

Sample app for the apache/grails-static-website guide [grails-vite-spa/v8](https://grails.apache.org/guides/grails-vite-spa/8/guide/index.html).

A two-tier integration: Grails 8 `rest_api` backend + Vite/React SPA frontend, packaged into a single bootJar.

`initial/` contains just the vanilla Grails 8 `rest_api` starter. `complete/` adds the Book domain, the API, the SPA, and the Gradle wiring that copies the built SPA into `backend/src/main/resources/public/` so a single `./gradlew :backend:bootJar` ships both halves at the same origin (no CORS).

## Dev

```bash
git clone -b grails8 https://github.com/grails-guides/grails-vite-spa.git
cd grails-vite-spa/complete
# In one shell:
./gradlew :backend:bootRun           # http://localhost:8080
# In a second shell:
cd frontend && npm install && npm run dev   # http://localhost:5173 with Vite proxy to backend
```
