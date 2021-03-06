!!! important "Quick Look"
    From the CLI:
    ```
    $ floyd stop <username>/projects/<project_name>/<job_number>
    ```

    From floydhub.com:
    ![Stop Job](../img/stop_job.jpg)


You can stop a queued or running job using Floyd CLI or using the web interface
on [floydhub.com](https://www.floydhub.com).

## Using the CLI
A job can be stopped using the `floyd stop` command and passing it the name of
your job, as shown below:

```
$ floyd stop mckay/projects/ssh/2
Experiment shutdown request submitted. Check status to confirm shutdown
```

Floyd CLI is fairly smart at resolving job names. It defaults to using your
username, the project initialized in the directory you're working in, and the
latest job number. So if you don't pass a job name to `floyd stop`, it will
stop your most recent job. Here are a couple examples of shortened job names
that are valid:

```
# Stops the most recent job for your user's project called 'foo'
$ floyd stop foo
```

```
# Stops job 2 for your user's project called 'foo'
$ floyd stop foo/2
```

To check the status of your job to make sure it has shut down properly, use the
`floyd status` command, as shown below:

```
$ floyd status mckay/projects/ssh/2
JOB NAME                     CREATED         STATUS      DURATION(s)  INSTANCE    DESCRIPTION
---------------------------  --------------  --------  -------------  ----------  -------------
mckay/projects/ssh/2         47 seconds ago  shutdown             24  c1
```

The same job-name shortcuts available for `floyd stop` are available whenever
you need to specify a job name, including with `floyd status <job_name>`.

## Using floydhub.com
On the project page, click the `Cancel` button below the icon that shows the status of your job, as shown in the picture below:

![Stop Job](../img/stop_job.jpg)

Then click the `Confirm` button in the modal that pops up:
![Stop Job Confirm](../img/stop_job_modal.jpg)

The status of your job will update to `Shutdown` when your job has successfully
been canceled.
