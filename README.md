# Simple GitHub API
I used **GitHub API** for **.NET** (**Octokit.net**) to demonstrate the basic use of GitHub API in **Windows Form Applications** in **C#.NET**.<br>

>Initially, My Windows Form application looks like:

<img src="https://f4e7137fefea07b0fae4c8ffd7320e68e7aa0823-www.googledrive.com/host/0B9svjAuZEeT4YVM3M1hzdGVxUzQ/ga1.jpg">

Enter appropriate **GitHub user name** in the textbox and hit **OK**.<br>
Code to get information of the user works as follows:

- First we need to create object of **`GitHubClient`** with **`ProductHeaderValue`** as argument. Here, **`ProductHeaderValue`** simply requires the name of the application which uses API (in our case name will be: **SimpleGitHubAPI**).
```C#
var github = new GitHubClient(new ProductHeaderValue("SimpleGitHubAPI"));
```
- Now, use **`User.Get`** of **`GitHubClient`** to get the information of the user.
```C#
var user = await github.User.Get(uName);
```
- Here, **`uName`** is a string variable, which stores the user name specified by the user.
```C#
string uName = textBox1.Text;
 ```
- Variable **`user`** will store the result generated by **`github.User.Get(uName)`**.
- Now, We just need to display those results in the form using a labels as:
```C#
label1.Text = "Name: " + user.Name
    + "\nSystem-wide ID: " + user.Id
    + "\nE-mail: " + user.Email
    + "\nAccount Type: " + user.Type
    + "\nFollowers: " + user.Followers
    + "\nFollowing: " + user.Following
    + "\nTotal Public Repos: " + user.PublicRepos
    + "\nTotal Private Repos: " + user.TotalPrivateRepos
    + "\nCreated at: " + user.CreatedAt;
```

For example, if I enter **H-Darji** in the textbox and hit OK, then it will fetch basic information of the user **H-Darji** from the database and displays it in the form as follow:

>Example: Information of user H-Darji:

<img src="https://f4e7137fefea07b0fae4c8ffd7320e68e7aa0823-www.googledrive.com/host/0B9svjAuZEeT4YVM3M1hzdGVxUzQ/ga3.jpg">

For more information about **`Octokit.net`**:
- <a href="https://github.com/octokit/octokit.net">Octokit.net on GitHub</a>
- <a href="http://octokitnet.readthedocs.io/en/latest/">Octokit.net Documention</a>

###### Thank you for visit.
