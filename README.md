# Rust Webserver Tutorial

### Commit 1 Reflection

The first line on the `handle_connection()` function reads the data on the TcpStream given from the `stream` parameter.

The second line "parses" the data from the read data. The first method `lines()` splits the data by a newline and returns the iterator. The second method `map()` will execute the closure with every element on the iterator as the argument. In this case, every line will be unwrapped and return the iterator of the transformed elements. The third method `take_while()` will execute the closure with every element on the iterator as the argument and only yields the element if the closure returns true. On this case, we only yield the element if the element is not empty. The last method `collect()` converts the iterator to a collection, in this case we specified that we want a `Vec(_)`.

The last line just prints out the data. The `?` means that this print is intended for debugging, the `#` means to pretty print the given data.

### Commit 2 Reflection

![Commit 2 screen capture](/assets/images/commit2.png)

### Commit 3 Reflection

We refactored to use an if statement when initializing the status line for the response and the HTML filename to reduce repeated coded.

![Commit 3 screen capture](/assets/images/commit3.png)

### Commit 4 Reflection

The /sleep is slow because we intendedly asked the thread to sleep for 10 seconds before returning a response with the ```thread::sleep()``` function.

### Commit 5 Reflection

The ThreadPool is implemented by making a vector of workers where the workers will create a thread to run the job. We are using channels to bridge communitaction between the ThreadPool and Worker. The receiver is wrapped with Mutex to avoid race conditions and Arc to avoid borrowing the receiver.