# aba-routing-number-validator
Validate ABA bank routing numbers

I took the requiments from the following videos.

https://www.youtube.com/watch?v=5wAE3E5zBe4

https://www.youtube.com/watch?v=D0jY_CuzcGw

Validator implments the 73973972 weights + check digit algorithm

Little to no testing was done beyond the unit test in the module. 

**example**
```package main

import (
	"fmt"

	v "github.com/bytetwiddler/aba-routingnumber-validator"
)


/* 
 * Ignoring errors for clarity.
 * There are only 2 public functions:
 *
 * 1) ValidateAbaRoutingNumber(a []int) (bool, error)
 *     If you create a slice of int you can just and pass it to
 *     ValidateAbaRoutingNumber() and be done.
 *
 * 2) StringSlicer(a string) ([]int, error) 
 *     A utility function that takes the routing number as a string and 
 *.    converts it to a slice of int, so you can pass it into 
 *.    ValidateAbaRoutingNuber(). This helps getting around golang 
 *     assuming 012312312 is an out of bounds octal.
 */ 
 
func main() {
	slice, _ := v.StringSlicer("123123123") // this is valid 
	res, _ := v.ValidateAbaRoutingNumber(slice)
	fmt.Println(res)
}
```
