# revnsl in [R]

## Reverse DNS lookup in [R]

I could not find a proper way to do a reverse DNS lookup in [R].
In other programming languages you can do a gethostbyaddr, but this function is lacking in [R].
It was frustrating to see the amount of misinformation online.
There is a internal function called nsl, but it can only do forward lookups.
Trying to use nsl to do a reverse lookup with the in-addr.arpa domain failed as well, as it expects to find an 'A' type record and not a 'PTR'.

## Solution

There is library in CRAN called iptools.
For Linux and Mac users, you can get it using:

  > install.packages("iptools")
  
For Windows users, you will need to install the latest version from github with devtools. 
The current CRAN version does not support DNS resolution, but this was recently added for Windows as well.

  > devtools::install_github("hrbrmstr/iptools")
  
Once you've installed the library, you can use the function:
  
  > ip_to_hostname("8.8.8.8")
  [[1]]
  [1] "google-public-dns-a.google.com"
