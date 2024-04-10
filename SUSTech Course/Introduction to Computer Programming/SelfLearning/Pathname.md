#### Pathname

**The Definition**

Each directory and file in the file system has a special location on the file tree, which is called the *pathname*, and you can think of a street address.

**How Pathnames Work**

> [!NOTE]
>
> Each file or directory has a unique pathname.

1. All absolute pathnames start from the root directory
2. The pathname works from the root directory to the file or directory that you wish to identify
3. A slash is placed between each level in the path name to separate each directory name from the previous level.

**An Example of Locating User jshmoe's home directory**

```java
/mnt/ncsudrive/j/jshmoe			
```

**The Example of Understanding a Location Data in Java**

```
[I@b4c966a
```

At very first we will find it is very hard to be understood.

So we will break it apart with the help of ChatGPT.

The first part is **[I** which has a meaning of that this is a array of integers.

The second part is **@**, which is a transitive sign.

The third part is b4c966a, which is the representation of the hash code of this array in hexadecimal, in other words it is just the presentation of the location of the storage.

**Other Example of the Array Hash Code**

```
[Ljava.lang.String;@6e8cf4c6
```

We can also separate into three parts.

The first part is **[Ljava.lang.String;** which imply that it is an array of strings.

The second part is **@** which is a transitive word.

The third part is **6e8cf4c6** which is the hash code of the array in hexadecimal.

```
[D@5e2de80c
```

We can also separate into three parts.

The first part is **[D** which imply that it is an array of double.

The second part is **@** which is a transitive word.

The third part is **5e2de80c** which is the hash code of the array in hexadecimal.

```
[Z@2f4d3709
```

We can also separate into three parts.

The first part is **[Z** which imply that it is an array of booleans.

The second part is **@** which is a transitive word.

The third part is **2f4d3709** which is the hash code of the array in hexadecimal.

**Other Resources**

https://e115.engr.ncsu.edu/pathnames/#:~:text=All%20absolute%20pathnames%20start%20from%20the%20root%20directory,file%20or%20directory%20has%20a%20unique%20path%20name.

