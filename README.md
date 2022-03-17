# Minimal reproduction for the SW download issue

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 13.1.2.

## Production build with http-server

Run `npm build:serve` and navigate to `127.0.0.1:50000`

## Replication instructions

1) Run the app with `npm build:serve`
2) Wait until the serviceworker starts the asset download - you should see a bunch of requests in the network tab
3) Go offline while it's still downloading
4) The app can now never go offline, even if you refresh the page while online again - the assets are never retried

## Additional notes

The babel node_modules contents were copied into the `/assets` directory so that there are 1000s of assets downloaded by the serviceworker. These were just used for demo purposes - if there are only a few assets, the issue becomes harder to replicate. None of the source code in that directory is my work.
