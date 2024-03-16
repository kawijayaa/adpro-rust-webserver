# Rust Webserver Tutorial

### Commit 1 Reflection

The first line on the `handle_connection()` function reads the data on the TcpStream given from the `stream` parameter.

The second line "parses" the data from the read data. The first method `lines()` splits the data by a newline and returns the iterator. The second method `map()` will execute the closure with every element on the iterator as the argument. In this case, every line will be unwrapped and return the iterator of the transformed elements. The third method `take_while()` will execute the closure with every element on the iterator as the argument and only yields the element if the closure returns true. On this case, we only yield the element if the element is not empty. The last method `collect()` converts the iterator to a collection, in this case we specified that we want a `Vec(_)`.

The last line just prints out the data. The `?` means that this print is intended for debugging, the `#` means to pretty print the given data.
