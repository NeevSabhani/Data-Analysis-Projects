# Complex Calculator -- Turing Complete

The primary purpose of our complex number library is to empower users to work seamlessly with complex numbers using a wide range of mathematical functions. The library supports the four elementary operations alongside trigonometric, hyperbolic trigonometric, inverse trigonometric, and inverse hyperbolic trigonometric functions.

## Getting Started

Follow these instructions to set up the project on your local machine for development and testing. Additional guidance for deployment on a live system is provided in the deployment section.

### Prerequisites

This project utilizes **Catch2** for unit testing individual functions. To get Catch2, refer to the instructions at [Catch2 GitHub Repository](https://github.com/catchorg/Catch2). Additionally, we use GitHub Classroom for educational purposes. To install it, run the following command:

```
gh install github/gh-classroom
```

### Installing

Below is a step-by-step guide to setting up your development environment:

1. Remove any existing `main` and `main-test` files to ensure a clean build (from the root directory):

   ```
   rm main
   rm main-test
   ```

2. Generate the required files by executing the following commands:

   ```
   make main
   make main-test
   ```

3. Run the program or the test cases using:

   ```
   ./main
   ./main-test
   ```

Upon running the test cases, you should see output similar to this:

```bash
Randomness seeded to: 2975693927
Running stests on equalsEquals
...
All tests passed (62 assertions in 38 test cases)
```

## Running the Tests

To execute the tests, follow the steps outlined above to create the `main-test` file.

### End-to-End Testing

In addition to unit testing with Catch2, the main program (`main`) allows you to manually test the library's functionality. After building `main`, you can run it with:

```
./main
```

Here’s an example interaction:

```
Hello World
Enter b: 2+4i
a = 5 + 6i
b = 2 + 4i
a + b = 7 + 10i
a * b = -14 + 32i
a / b = 1.7 - 0.4i
|a| = 7.81025
complex conjugate of a = 5 - 6i
norm of a = 7.81025
abs of a = 7.81025
exp(a) = 142.502 - 41.4689i
Complex number example: 1 + 2i
The conjugate is: 1 - 2i
The magnitude is: 2.23607
The phase in Radians is: 1.10715
The norm is: 2.23607
The sqrt is: 1.27202 + 0.786151i
The natural log is: 0.804719 + 1.10715i
The sin is: 3.16578 + 1.9596i

------ OTHER FUNCTION TESTING ------

The real part is: 5
The imaginary part is: 6
The log (base 10) is: 0.892665 + 0.380467i
a^b is: -1.56463 - 0.957315i
a^2.7 is: -183.495 + 180.163i
2.7^a is: 136.038 - 45.6371i
The cube root is: 1.90006 + 0.571185i

(a == b) is: false
(a != b) is: true

sin(a) = -193.43 + 57.2184i
cos(a) = 57.2191 + 193.428i
tan(a) = -6.68523e-06 + 1.00001i

The asin is: 0.690716 + 2.74935i
The acos is: 0.88008 - 2.74935i
The atan is: 1.48822 + 0.0980105i
The acsc is: 0.0816617 - 0.09853i
The asec is: 1.48913 + 0.09853i
The acot is: 0.0825743 - 0.0980105i

The asinh is:2.74787 + 0.872018i
The acosh is: 2.74935 + 0.88008i
Rounded to 2 decimal places: 2.75 + 0.88i
The atanh is: 0
The acsch is: 0.0822711 - 0.0981864i
The asech is: 0.09853 - 1.48913i
The acoth is: 0
The complex number rotated by pi/6 radians is: 1.33013 + 7.69615i
```

### Coding Style Tests

Coding style tests involve unit testing for specific functions. As previously mentioned, Catch2 is used for this purpose. Below is an example of a test case for the `arg` function:

```
TEST_CASE("Quick Catch2 test on Arg (arg)", "[Arg]")
{
  cout << "Running stests on Arg" << endl;
  REQUIRE((arg(Complex(3.0,2.0))) == atan2(2.0,3.0));
  REQUIRE((arg(Complex(3.0,0.0))) == atan2(0.0,3.0));
  REQUIRE((arg(Complex(4.0,-5.0))) == atan2(-5.0,4.0));
  REQUIRE((arg(Complex(0.0,0.0))) == atan2(0.0,0.0));
}
```

## Deployment

For deploying this library on a live system, ensure all dependencies are installed and configurations align with your production environment. Additional deployment-specific notes can be added here as required.

## Built With

- [GNU Tools](https://www.gnu.org/software/gcc/) - GNU compiler tools
- Any additional tools you may need...

## Structure

The project structure is as follows:

```text
.
├── CONTRIBUTING.md
├── image.png
├── lib
│   ├── abs.cpp
│   ├── abs.h
│   ├── ...
├── main
├── main-debug
├── main-test
├── Makefile
├── README.md
|── LICENSE.md
├── replit.nix
├── src
│   ├── a.out
│   ├── CMakeLists.txt
│   └── main.cpp
└── tests
    ├── catch_amalgamated.cpp
    ├── ...
```

## Building

To build the project, create a build directory (e.g., `build/`), and run `make` within that directory:

```bash
make main           # Compiles the main file
./main              # Executes the main file
make main-test      # Compiles and runs the test cases
make main-debug     # Builds a debug version of main
```

## Functionality

The library's primary objective is to provide users with robust tools to perform operations on complex numbers. It supports elementary operations, trigonometric functions, hyperbolic functions, and their respective inverses.

Functions include, but are not limited to: calculating magnitude (`abs`), conjugates (`conj`), and trigonometric functions (`sin`, `cos`, `tan`). Additional advanced functionalities like `exp`, `log`, and `root` extend the library’s capabilities. For detailed descriptions, refer to the function definitions.

## .gitignore

The `.gitignore` file excludes the build folder and personal settings to protect sensitive data and prevent unnecessary files from being committed.

## Contributing

Please review the [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct and instructions for submitting pull requests.

## Versioning

We use [Semantic Versioning (SemVer)](http://semver.org/) for version control. Refer to the [tags on this repository](https://github.com/your/project/tags) for available versions.

## Authors

This project was developed by Matthew Robson, Soumik Chemudupati, Neev Sabhani, Ashwin Geeni, and Saul Scott.

## License

This project is licensed under the MIT License. See the [LICENSE.md](LICENSE.md) file for details.

## Acknowledgments

We extend our gratitude to Mr. James Shockey and the LASACS department for their invaluable support and guidance throughout the development of this project.

