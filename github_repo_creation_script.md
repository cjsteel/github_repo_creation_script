# github_repo_creation_script
Dead simple python script for creating new github repositories while enforcing repository naming convention and taking care of unique naming/numbering scheme.

## Requirements

* pyGithub
  * `easy_install PyGithub` or
  * `pip install PyGithub`
  * or clone it on Github.
* github account token
  * access to reading and creating repos.

## Actions

* The script will read out all existing repositories for the given token's account and if the given prefix is allowed, the script will create a new repo with the prefix and a number that is next in the sequence of existing repos, the rest of the name and description of repository is arbitrary but mandatory arguments.

## Prefix modification

* Modify the list of allowed prefixes as required.
* The naming convention that has to be adhered to is this:

```shell
{anylengthprefix}{3-digit number}_{repo_name_with_underscores_not_spaces}
```

The underscore between number and name is mandatory and inserted by this script.

## Usage

```shell
create_github_repo.py [-h] -t {p,s,h,u,lib} -n NAME -d DESCRIPTION
arguments:
  -h, --help            show this help message and exit
  -t {p,s,h,u,lib}, --type {p,s,h,u,lib} 
```



                        Initial character of repo name indicating type of repository.

  -n NAME, --name NAME  Repo name after numbering and type indication.

  -d DESCRIPTION, --description DESCRIPTION
                        Description of repository content.

<b>Example:</b>
Create a new repo: 

```shell
c:>python create_github_repo.py --type p --name repo_creating_script_test_repo -d "This is a test repo for repo creating script"
```

Custome example

```shell
python create_github_repo.py --type ansible-role --name template -d "This is a test repo for repo creating script"
```



```shell
Create repo p007_repo_creating_script_test_repo ? yes for yes: yes
repo p007_repo_creating_script_test_repo created for user andlier
```

In this example p001 to p006 was already created, so p007 was created.

