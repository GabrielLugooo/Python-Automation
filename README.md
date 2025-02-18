<img align="center" src="https://media.licdn.com/dms/image/v2/D4D16AQGUNxQ7NSC05A/profile-displaybackgroundimage-shrink_350_1400/profile-displaybackgroundimage-shrink_350_1400/0/1738695150340?e=1744243200&v=beta&t=oXX-ixT9bR3dJcYCLv4KBs5wjKFoeP0524kFGHQMYmQ" alt="gabriellugo" />

# PYTHON ALGORYTHM UPDATE FILE

<a href="https://github.com/GabrielLugooo/Python-Algorithm-Update-File" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.shields.io/badge/Python%20Algorythm%20English-000000" alt="Python Algorythm English" /></a>
<a href="https://github.com/GabrielLugooo/Python-Algorithm-Update-File/blob/main/README%20Spanish.md" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.shields.io/badge/Python%20Algorythm%20Spanish-green" alt="Python Algoryth Spanish" /></a>

### Objective

Python Algorythm Update File it's an Algorythm that removes IP addresses identified in a "remove_list" variable from the "allow_list.txt" file of approved IP addresses.

This algorithm involve opening the file, converting it into a string to read, and then converting this string into a list stored in the variable "ip_addresses".

Next, iterate through the IP addresses in "remove_list". With each iteration, evaluate whether the item was part of the "ip_addresses" list. If it is, applies the ".remove()" method to it to remove the item from "ip_addresses".

After this, use the ".join()" method to convert "ip_addresses" back into a string so could overwrite the contents of the "allow_list.txt" file with the revised list of IP addresses.

### Skills Learned

- Python Technologies.
- Protect networks, information and data using an Algorythm that identifies allowed and not allowed IP´s adress techniques.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Technologies Used

![Static Badge](https://img.shields.io/badge/Python-000000?logo=python&logoSize=auto)

### Project

In many organizations, access to restricted content is controlled by a list of allowed IP addresses. The "allow_list.txt" file identifies these IP addresses.

A separate allow list identifies IP addresses that should no longer have access to this content. I created an algorithm to automate updating the "allow_list.txt" file and remove these IP addresses that should no longer have access.

#### Open the file containing the allow list

For the first part of the algorithm, open the file "allow_list.txt" . First, assign this file name as a string to the variable "import_file" :

```sh
# Assign `import_file` to the name of the file
import_file = "allow_list.txt"
```

Then assign the “remove_list” file to a list of IP addresses that are no longer allowed to access restricted information:

```sh
# Assign `remove_list` to a list of IP addresses that are no longer allowed to access restricted information.
remove_list = ["192.168.97.225", "192.168.158.170", "192.168.201.40", "192.168.58.57"]
```

Then use a "with" statement to open the file:

```sh
# Build `with` statement to read in the initial contents of the file
with open(import_file, "r") as file:
```

In the algorithm, the "with" statement is used with the ".open()" function in read mode to open the allowlist file for reading purposes. The purpose of opening the file is to allow access to the IP addresses stored in the allowlist file. The "with" keyword will help in managing the resources by closing the file after exiting the with statement .

In the code "with open(import_file, "r") as file:" , "the open()" function has two parameters. The first identifies the file to import and then the second indicates what you want to do with the file. In this case, "r" indicates that you want to read it. The code also uses the as keyword to assign a variable called "file", "file" stores the output of the ".open()" function as you work inside the with statement .

#### Read the contents of the file

To read the contents of the file, use the ".read()" method to convert it to a string:

```sh
with open(import_file, "r") as file:

  # Use `.read()` to read the imported file and store it in a variable named `ip_addresses`
  ip_addresses = file.read()
```

By using an ".open()" function that includes the "r" argument for "read", you can call the ".read()" function in the body of the "with" statement. The ".read()" method converts the file to a string and allows to read it. Apply the ".read()" method to the file variable identified in the with statement .

Then, assign the string output of this method to the "ip_addresses" variable .

In short, this code reads the contents of the "allow_list.txt" file into a string format which allows you to use the string to organize and extract data in the Python program.

#### Convert string to list

To remove individual IP addresses from the allow list, you needed them to be in list format. So, next use the ".split()" method to convert the string "ip_addresses" into a list:

```sh
# Use `.split()` to convert `ip_addresses` from a string to a list
ip_addresses = ip_addresses.split()
```

".split()" function is called by adding a string variable to it. It works by converting the contents of a string into a list. The purpose of splitting "ip_addresses" into a list is to make it easier to remove IP addresses from the allow list. By default, the ".split()" function splits text by whitespace into list items.

".split()" function takes the data stored in the variable "ip_addresses" , which is a string of IP addresses separated by whitespace, and converts this string into a list of IP addresses. To store this list, you've to reassign it to the variable "ip_addresses".

#### Iterate through the delete list

A key part of the algorithm involves iterating through the IP addresses that are elements in the "remove_list". To do this, you need to incorporate a "for" loop:

```sh
# Build iterative statement
# Name loop variable `element`
# Loop through `ip_addresses`
for element in ip_addresses:
```

The "for" loop in Python repeats the code for a specific sequence. The general purpose of the "for" loop in a Python algorithm like this is to apply specific code statements to all elements of a sequence.

for keyword starts the "for" loop. It is followed by the element loop variable and the "in" keyword. The "in" keyword instructs to iterate through the "ip_addresses" sequence and assign each value to the element loop variable.

#### Delete IP addresses that are on the delete list

The algorithm requires removing any IP addresses from the allow list, "ip_addresses", that are also contained in "remove_list". Because there were no duplicates in "ip_addresses", you are able to use the following code to do this:

```sh
# Build iterative statement
# Name loop variable `element`
# Loop through `ip_addresses`
for element in ip_addresses:

    # Build conditional statement
    # If current element is in `remove_list`,
    if element in remove_list:

        # then current element should be removed from `ip_addresses`
        ip_addresses.remove(element)
```

First, inside min the "for" loop, create a condition that evaluated whether the element loop variable was found in the "ip_addresses" list. you will did this because applying ".remove()" to elements that were not found in "ip_addresses" could result in an error.

So inside that conditional, apply ".remove()" to "ip_addresses". you passed the loop variable element as an argument so that every IP address that was in the "remove_list" would be removed from "ip_addresses".

#### Update the file with the revised list of IP addresses

As the next step of the algorithm, you needed to update the allowlist file with the revised list of IP addresses. To do this, first you had to convert the list back into a string. Use the ".join()" method for this:

```sh
# Convert `ip_addresses` back to a string so that it can be written into the text file
ip_addresses = " ".join(ip_addresses)
```

".join()" method combines all the elements of an iterable into a string. The ".join()" method is applied to a string containing characters that will separate the elements of the iterable once they are joined into a string.

In this algorithm, use the ".join()" method to create a string from the "ip_addresses" list so that it can be passed as an argument to the ".write()" method when writing to the "allow_list.txt" file. Use the string (" ") (empty character) as a separator to tell Python to put each item on a new line.

Then use another "with" statement and the ".write()" method to update the file:

```sh
# Build `with` statement to rewrite the original file
with open(import_file, "w") as file:

  # Rewrite the file, replacing its contents with `ip_addresses`
  file.write(ip_addresses)
```

This time, you used a second argument of "w" with the "open()" function in the "with" statement . This argument indicates that you want to open a file to write over its contents. By using this "w" argument , you can call the ".write()" function in the body of the "with statement. The ".write()" function writes string data to a specified file and replaces any existing file contents.

In this case, you wanted to write the updated allow list as a string to the "allow_list.txt" file . This way, the restricted content will no longer be accessible to any IP addresses that have been removed from the allow list.

To rewrite the file, you added the ".write()" function to the file object file you identified in the "with" statement. You passed the "ip_addresses" variable as an argument to specify that the contents of the file specified in the "with" statement should be replaced with the data in this variable.

#### Read the file with the revised list of IP addresses

As a final step in the algorithm, you needed to read the updated allowlist file with the revised list of IP addresses.
"with" statement again , "the open()" function , the "r" argument , the code also uses the as keyword to assign a variable called "file", with the function "with open(import_file, "r") as file:".

```sh
# Build `with` statement to read in the updated file
with open(import_file, "r") as file:

    # Read in the updated file and store the contents in `text`
    text = file.read()

# Display the contents of `text`
print(text)
```

Apply the".read()" method to the file variable identified in the with statement. Then, you assigned the string output of this method to the text variable .

Then apply the "print()" function and assigning the text variable we can print the contents of the revised "import_file" file on the screen in string format.

### Limitations

Python Algorythm Update File it's just for educational purpose under the MIT License.

---

<h3 align="left">Connect with me</h3>

<p align="left">
<a href="https://www.youtube.com/@gabriellugooo" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.icons8.com/?size=50&id=55200&format=png" alt="@gabriellugooo" height="40" width="40" /></a>
<a href="http://www.tiktok.com/@gabriellugooo" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.icons8.com/?size=50&id=118638&format=png" alt="@gabriellugooo" height="40" width="40" /></a>
<a href="https://instagram.com/lugooogabriel" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.icons8.com/?size=50&id=32309&format=png" alt="lugooogabriel" height="40" width="40" /></a>
<a href="https://twitter.com/gabriellugo__" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.icons8.com/?size=50&id=phOKFKYpe00C&format=png" alt="gabriellugo__" height="40" width="40" /></a>
<a href="https://www.linkedin.com/in/hernando-gabriel-lugo" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.icons8.com/?size=50&id=8808&format=png" alt="hernando-gabriel-lugo" height="40" width="40" /></a>
<a href="https://github.com/GabrielLugooo" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.icons8.com/?size=80&id=AngkmzgE6d3E&format=png" alt="gabriellugooo" height="34" width="34" /></a>
<a href="mailto:lugohernandogabriel@gmail.com"> <img align="center" src="https://img.icons8.com/?size=50&id=38036&format=png" alt="lugohernandogabriel@gmail.com" height="40" width="40" /></a>
<a href="https://linktr.ee/gabriellugooo" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://simpleicons.org/icons/linktree.svg" alt="gabriellugooo" height="40" width="40" /></a>
</p>

<p align="left">
<a href="https://github.com/GabrielLugooo/GabrielLugooo/blob/main/README.md" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.shields.io/badge/English%20Version-000000" alt="English Version" /></a>
<a href="https://github.com/GabrielLugooo/GabrielLugooo/blob/main/Readme%20Spanish.md" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.shields.io/badge/Spanish%20Version-Green" alt="Spanish Version" /></a>
</p>

<a href="https://linktr.ee/gabriellugooo" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.shields.io/badge/Credits-Gabriel%20Lugo-green" alt="Credits" /></a>
<img align="center" src="https://komarev.com/ghpvc/?username=GabrielLugoo&label=Profile%20views&color=green&base=2000" alt="GabrielLugooo" />
<a href="" target="_blank" rel="noreferrer noopener"> <img align="center" src="https://img.shields.io/badge/License-MIT-green" alt="Last Edited" /></a>
