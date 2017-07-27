# ldrgen

This is ldrgen, a small experimental random C program generator.


## Introduction

This program is a generator of C code: On every call it generates a new
random C function and prints it to the standard output. The generator is
"liveness-driven", which means that it tries to avoid generating dead code:
All the computations it generates are (in a certain, limited sense) actually
used to compute the function's return value. Other than this, ldrgen does
not do much to ensure that its output resembles anything like "real"
programs.

See [Csmith](https://github.com/csmith-project/csmith) for another C program
generator that is in many ways more sophisticated than this.

A paper describing ldrgen has been accepted for presentation at the LOPSTR
2017 conference. A preprint is at
[lopstr2017_ldrgen_preprint.pdf](lopstr2017_ldrgen_preprint.pdf).


## Examples

Here is a small example program generated by ldrgen:

```c
/* Generated by Frama-C */
// Generated by ldrgen
// Seed: 82678471
// Command line arguments: -ldrgen -ldrgen-stmt-depth 2 -ldrgen-expr-depth 3
short fn1(char p, double p_5, unsigned long p_7, unsigned int p_11,
          unsigned short p_17, long long p_21, double p_25,
          unsigned char p_27)
{
  double v_51;
  long v_49;
  float v_47;
  unsigned char v_45;
  unsigned long long v_43;
  short v_41;
  unsigned int v_39;
  signed char v_37;
  long long v_35;
  unsigned short v_33;
  unsigned long v_31;
  double v_29;
  unsigned int v_23;
  int v_19;
  unsigned long long v_15;
  long long v_13;
  unsigned short v_9;
  unsigned char v;
  short result;
  v_51 = p_5;
  v_47 = -7300539349.21f;
  v_43 = 18446744073709511602ULL;
  v_41 = (short)-20504;
  v_35 = -26125LL;
  v_31 = 4169455334UL;
  v_29 = 670.493914988;
  v_23 = 4245290602U;
  v_19 = -2470;
  v_13 = 1064779636LL;
  v_9 = (unsigned short)45625;
  v_49 = (long)(- ((v_51 - (double)(unsigned short)38061) / ((double)(signed char)53 * p_25 + (double)404)));
  if ((unsigned int)(-3.2054506015e+38 * (double)((unsigned long)4864751150.7 * p_7)) + (
      (unsigned int)(~ v_41) - (p_11 - (unsigned int)v_47)) == (unsigned int)(
      (double)(- v_49) / (- p_5 + (double)87))) {
    v_41 = (short)((long long)(- (p_7 - p_7)) + - p_21);
    v_9 = (unsigned short)((long long)p_17 + (long long)p_25 % (((long long)p - v_35) + 719LL));
    v_39 = (unsigned int)((int)(- ((float)(short)-21044 * 3.19873597495e+37f)));
    v_15 = (unsigned long long)(- ((unsigned long)(~ v_39) / 3082953060UL));
    v_23 = (unsigned int)(- ((v_15 | 18446744073709503346ULL) % 4294921912ULL));
  }
  else {
    v_45 = (unsigned char)(! (-33986LL + p_21 / -107602102LL));
    v_13 = (long long)(~ (- ((long)v_45 * -128552529L)));
    v_31 = 74UL;
    v_29 = (double)(~ ((unsigned long long)p_7 - 18446744073406306995ULL * v_43));
    v_15 = (unsigned long long)(172U + ~ (~ p_11));
  }
  while (~ v_23 < 1U) {
    v_19 = (int)((char)v_29) % 125;
    v_37 = (signed char)-9951321808.38;
    v_33 = (unsigned short)(((double)v_37 * (p_5 - (double)p)) / (double)18446744073294828742ULL);
    v_15 = (unsigned long long)(((double)((int)v_33 * 78) * - p_5) * (double)(
                                (long long)(~ p_7) / ((215LL - v_35) + 852LL)));
    v_13 = (long long)(~ (~ (! p_11)));
    v_23 = (unsigned int)(2729386713.2f + (float)(! p_21 * (long long)v_31));
  }
  if ((unsigned long long)((float)(p_7 / 64249UL + (unsigned long)((unsigned int)v_9 * p_11)) * (
                           (1.88298916636e+38f - (float)v_13) - (float)(
                           v_15 % 203ULL))) <= (unsigned long long)((long long)(
                                                                    -120 / (
                                                                    (int)p_17 + 71)) + (
                                                                    (long long)v_19 - p_21)) * 4294946671ULL) {
    v = (unsigned char)(~ ((unsigned long long)p_5 - 42536ULL) % (unsigned long long)(
                        (long)(- -6414484372.37) % 43253L + 627L));
    result = (short)((84 + (int)(- v)) + (int)(- p));
  }
  else result = (short)-24120;
  return result;
}
```


## TODOs

Many more C language constructs should be added.


## Installation

This program is implemented as a plugin for Frama-C <http://frama-c.com/>.
It should run on all Unix-like platforms with Frama-C and standard build
tools.

Your favorite package manager may provide a Frama-C package that installs
all you need. Otherwise, the easiest way to install Frama-C is to first
install OPAM, the OCaml package manager <http://opam.ocaml.org/>. You can
then run

    opam install frama-c

or

    opam install frama-c-base

The latter should ask you for fewer additional system libraries to install,
but I have not tested ldrgen with it.

With Frama-C installed and the `frama-c` executable in your path, you can
compile ldrgen by running `make` and install it with `make install`. It will
be installed in Frama-C's plugin directory. You can remove it again by
running `make uninstall`.

For now, run ldrgen as `frama-c -ldrgen`. See `frama-c -ldrgen-h` for
documentation on some command-line flags that can affect the generated code.


## Contact

This program was written by Gergö Barany <gergo@tud.at>. It lives at
<https://github.com/gergo-/ldrgen>.

Comments, questions, bug reports, feature requests, and patches are welcome!


## Copying

This program is free software: you can redistribute it and/or modify it
under the terms of the GNU General Public License as published by the Free
Software Foundation, either version 3 of the License, or (at your option)
any later version.

This program is distributed in the hope that it will be useful, but WITHOUT
ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or
FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for
more details.

You should have received a copy of the GNU General Public License along with
this program (file LICENSE). If not, see <http://www.gnu.org/licenses/>.
