# Quick Start Guide for Test Management Tool (tmt)

This quick start guide provides a brief overview to get you up and running with tmt.

### Installation

To install tmt, run the following command:

```sudo dnf install -y tmt```

### Initialize a New Project

Create a new directory for your project and navigate into it:

```
mkdir tmt-quickstart
cd tmt-quickstart
```

Initialize the project with a simple smoke test:

```
tmt init --template mini
```

### Run Tests

Execute the smoke test locally:

```tmt run```

This will launch tmt test on your local machine. 
To see the results request for a report:

```tmt run -i run-01 report```

To run the test in a container or virtual machine, use:

```tmt run --all provision --how container```

or

```tmt run --all provision --how virtual```

To run particular test by its path 

```tmt run -all provision --how container test --name /tests/hello-world-shell```


### Create New Tests, Plans, and Stories

Generate a new shell test case:

```tmt test create --template shell /tests/hello-world-shell```

```--template shell``` creates ping-test folder with main.fmf and test.sh that is referred in fmf file

Create a new plan:

```tmt plan create --template base /plans/basic```

`--template base` services as a starting point for defining test plan and includes the essential elements of it such as dicovery and execution.

`--template full` contains everything from base template plus discover and prepare sections.   

`--template mini`  stripped down version containing only execution section


Start a new story:

```tmt story create --template base /stories/main```

`--template base` services as a starting point for defining test plan and includes the essential elements of it such as story summary and example.

`--template full` contains everything from base template plus description.   

`--template mini`  stripped down version containing only story and example sections.

### Linting

```tmt lint```

For more detailed information, refer to the [full documentation](https://tmt.readthedocs.io/en/stable/index.html)


