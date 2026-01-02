# explaination

when we check `localhost:8080/robots.txt` we can see the web crawler config. we have indication about `/.hidden/` path when we access it we can see a labyrinth of directories and README file with 34 characters with a troll message. we just need to find all read me and see if there is a difference. we can use the command `find` for that, but first of all we need to scrap all the readme in .hidden

# command

download everything from the web, with no parent, only les readme dans .hidden
`wget -r -np -e robots=off -A README http://localhost:8080/.hidden/` 

then we find for the right readme

`find . -type f -name README -exec wc -c {} \;`

and we have a readme with 90char and the flag:

`Index of /.hidden/whtccjokayshttvxycsvykxcfm/igeemtxnvexvxezqwntmzjltkt/lmpanswobhwcozdqixbowvbrhw/`

# use case

thoses directories are not meant to be public, and can divulge sensitive information likes configuration files.

# fix

the configuration of the web server should not allow to access thoses directories.
