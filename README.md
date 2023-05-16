# Effectra HTTP Server Handler

Effectra HTTP Server Handler is a package that provides a request handler implementation for handling HTTP requests by processing a stack of middlewares.

## Installation

You can install the package via Composer. Run the following command in your terminal:

```bash
composer require effectra/http-server-handler
```

## Usage

To use the Effectra HTTP Server Handler, follow these steps:

1. Create an instance of the `Effectra\Http\Server\RequestHandler` class, passing an array of middlewares as a parameter to the constructor.

2. Invoke the `handle()` method of the request handler, passing a `Psr\Http\Message\ServerRequestInterface` object as an argument. This method will process the middlewares stack and return a `Psr\Http\Message\ResponseInterface` object.

```php
use Effectra\Http\Server\RequestHandler;
use Effectra\Http\Foundation\RequestFoundation;
use Effectra\Http\Foundation\ResponseFoundation;

// Create an array of middlewares
$middlewares = [
    // Add your middlewares here
];

// Create a request handler instance
$requestHandler = new RequestHandler($middlewares);

// Create a server request
$request = RequestFoundation::createFromGlobals();

// Handle the request and get the response
$response = $requestHandler->handle($request);

// Send the response
ResponseFoundation::send($response);
```

## Contributing

Contributions are welcome! If you find any issues or want to contribute to this package, please feel free to submit a pull request or open an issue on the GitHub repository: [effectra/http-server-handler](https://github.com/effectra/http-server-handler)

## License

The Effectra HTTP Server Handler package is open-source software licensed under the [MIT license](https://opensource.org/licenses/MIT).