# Inertia Testbench
This package provides a skeleton for testing Inertia.js (with Vue) applications with Orchestra Testbench. It is designed to be installed inside a `conquest/skeleton-laravel` templated package, and allows for full-stack testing.

## Using Skeleton with Testbench
These instructions are designed with the `conquest/skeleton-laravel` template, but can be applied to other Laravel projects. Install the skeleton package:

```bash
composer require --dev conquest/inertia-testbench
```

Autoload the package to resolve the namespace properly inside your `composer.json` file:

```json
{
    "autoload-dev": {
        "psr-4": {
            "App\\": "vendor/conquest/inertia-testbench/skeleton/app/"
        }
    }
}
```

Add the following scripts to your `composer.json` file:

```json
{
    "scripts": {
        "node": "cd vendor/conquest/inertia-testbench/skeleton && npm run dev",
        "node-install": "cd vendor/conquest/inertia-testbench/skeleton && npm i"
    },
}
```

Execute the command to install the node modules:

```bash
composer run node-install
```

Ensure you have an `APP_KEY` set in your test case environment. This can be added inside the `testbench.yaml` file:

```yaml
env:
    APP_DEBUG: true
    APP_KEY: AckfSECXIvnK5r28GVIWUAxmbBSjTsmF
```

The server can then be run with both server and client:

```bash
composer run serve
```

```bash
composer run node
```

## With Dusk
It is suggested that for full-stack testing, Dusk should be used in conjunction with this package. Testbench comes equipped with a Dusk driver that will allow you to test your application in a real browser.

```bash
composer require --dev orchestra/testbench
```
