# Synchronous FingerprintJS

## Intro

This is a fork of [FingerprintJS](https://github.com/fingerprintjs/fingerprintjs). I needed a synchronous version of FingerprintJS so that fingerprint generated in &lt;head&gt;, because I need to add fingerprint in HTTP Request head in legacy code. It is too much effort to update legacy HTTP Request to Promise base. For trade-off, Synchronous FingerprintJS removed following asynchronous factors of fingerprint generating - `fonts`, `domBlockers`, `fontPreferences`, `audio`, `screenFrame`.

### Usage

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Synchronous FingerprintJS</title>
    <script src="../src/fp.js"></script>
    <script>
        var fpPromise = FingerprintJS.load();

        // async version
        fpPromise
            .then(fp => fp.get())
            .then(result => {
                console.log(result.visitorId);
            });

        // sync version
        console.log(FingerprintJS.getSync().visitorId);
    </script>
</head>

<body>

</body>

</html>
```

See https://github.com/fingerprintjs/fingerprintjs for more info.




