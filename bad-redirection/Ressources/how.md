# explaination

link are not direct link, but `https://localhost:8080/index.php?page=redirect&site=facebook` for example.
we can change it to any value, because they are verified and redirect no matter what

`http://localhost:8080/index.php?page=redirect&site=yahoo`

and get the flag


# risk 

link need to be from the base website not the site parameter value, this could be used for phishing, adverstising or anything since we manipualte redirection behavior

# fix

check the website parameter and its valid before redirecting. a better behavoir is to use the real link from the website.
