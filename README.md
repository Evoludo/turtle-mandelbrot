# turtle-mandelbrot
A Mandelbrot fractal generator written in a turtle graphics DSL.

## Invocation

### Standalone DSL interpreter 
To run the standalone DSL, run `./run_standalone.sh`.
The syntax is `./run_standalone.sh [-o output_filename] [-w width] [-h height] filename`.

### Mandelbrot generator
The `mandelbrot.tg` file contains the Mandelbrot fractal generator.
The size is hard-coded into the file as 640x480.
To run it, use the command `./run_standalone.sh -w 640 -h 480 mandelbrot.tg`.
There are several variables in the file that can be fiddled with:

Variable                           | Paramater
-----------------------------------|--------------------------------
`fp_scale`                         | Floating point scale. This changes the precision of the floating point calculation. Default is `1000`, e.g. `3.1415` becomes `3142`.
`x_min`, `x_max`, `y_min`, `y_max` | Complex plane window boundaries. Use these variables to change the centre and zoom of the fractal.
`width`, `height`                  | Output size. This should match the image size you called the interpreter with.
`max_iter`                         | Maximum iterations to run the Mandelbrot recurrance on. `10` is a good value to produce a result fast, but `20` and above looks nicer, at the expense of speed.
`max_r_sq`                         | Escape radius squared. There's no square root function in the language, so the radius comparison is kept in sqaured values. If the magnitude of the recurrance function value (squared) is less than this, then the point is in the Mandelbrot set; otherwise, it isn't.

The calculations for the outside colouring are also modifiable.
Fiddling with these is left as an exercise to the interested ;).

## Credits

The compiled DSL interpreter (everything contained in the Assignment3) was written by [Simon Fowler](http://simonjf.com), and is *NOT* covered by the GPL!
