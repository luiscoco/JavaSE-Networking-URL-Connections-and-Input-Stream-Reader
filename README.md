# JavaSE-Networking-URL-Connections-and-Input-Stream-Reader

https://github.com/luiscoco/JavaSE-Networking-URL-Connections-and-Input-Stream-Reader

This Java code performs a simple HTTP GET request to the URL **http://example.org** and prints the content of the response to the console.

The code imports necessary classes from the Java standard library for handling input/output and working with URLs:

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.MalformedURLException;
import java.net.URL;
import java.net.URLConnection;
```

The Main class is defined, and the main method is the entry point of the program:

```java
public class Main {
    public static void main(String[] args) {
        // Code goes here
    }
}
```

Inside the **main** method:

A URL object is created with the specified URL "http://example.org":

```java
URL url = new URL("http://example.org");
```

A URLConnection object is created by calling the openConnection method on the URL object:

```java
URLConnection urlConnection = url.openConnection();
```

The setDoOutput(true) method is called on the URLConnection object to indicate that the connection will be used for output:

```java
urlConnection.setDoOutput(true);
```

The connect() method is called to establish the connection to the URL:

```java
urlConnection.connect();
```

A BufferedReader is created to read from the input stream of the URLConnection:

```java
BufferedReader inputStream = new BufferedReader(
        new InputStreamReader(urlConnection.getInputStream()));
```

A while loop is used to read each line from the input stream and print it to the console until there are no more lines:

```java
String line = "";
while(line != null) {
    line = inputStream.readLine();
    System.out.println(line);
}
```

Finally, the inputStream is closed:

```java
inputStream.close();
```

The code handles exceptions, such as MalformedURLException and IOException, by printing error messages to the console:

```java
} catch(MalformedURLException e) {
    System.out.println("Malformed URL: " + e.getMessage());
} catch(IOException e) {
    System.out.println("IOException: " + e.getMessage());
}
```

In summary, this code makes an HTTP GET request to "http://example.org", reads the response, and prints it to the console.

```java
package com.timbuchalka;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.MalformedURLException;
import java.net.URL;
import java.net.URLConnection;

public class Main {

    public static void main(String[] args) {
        try {
            URL url = new URL("http://example.org");
            URLConnection urlConnection = url.openConnection();
            urlConnection.setDoOutput(true);
            urlConnection.connect();

            BufferedReader inputStream = new BufferedReader(
                    new InputStreamReader(urlConnection.getInputStream()));

            String line = "";
            while(line != null) {
                line = inputStream.readLine();
                System.out.println(line);
            }
            inputStream.close();

        } catch(MalformedURLException e) {
            System.out.println("Malformed URL: " + e.getMessage());
        } catch(IOException e) {
            System.out.println("IOException: " + e.getMessage());
        }
    }
}
```

![image](https://github.com/luiscoco/JavaSE-Networking-URL-Connections-and-Input-Stream-Reader/assets/32194879/514a073f-f89e-45ba-9e03-6e34c794b03f)

![image](https://github.com/luiscoco/JavaSE-Networking-URL-Connections-and-Input-Stream-Reader/assets/32194879/81520097-9938-47ce-bc87-dd084a80eeac)
