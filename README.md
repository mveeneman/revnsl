# revnsl in [R]

## Reverse DNS lookup in [R]

I could not find a proper way to do a reverse DNS lookup in [R].
In other programming languages you can do a gethostbyaddr, but this function is lacking in [R].
There is a function called nsl, but it can only do forward lookups.
Trying to do a reverse lookup with the in-addr.arpa domain failed as well, as it expects to find an 'A' type record and not a 'PTR'.

## Solution

Luckily in [R] there is a library in CPAN called iptools.
You can get it using:

  > install.packages("iptools")
  
Once you've installed the library, you can use the function:
  
  > ip_to_hostname("8.8.8.8")
  [[1]]
  [1] "google-public-dns-a.google.com"
