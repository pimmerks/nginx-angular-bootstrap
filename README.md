Add this to your multi stage Dockerfile.

```
FROM ppiimm123/nginx-angular-bootstrap as runtime

## From ‘builder’ stage copy over the artifacts in dist folder to default nginx public folder
COPY --from=builder /ng-app/dist /usr/share/nginx/html

CMD ["nginx", "-g", "daemon off;"]

```