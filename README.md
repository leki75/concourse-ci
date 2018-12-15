Concourse CI
============

Start with [all-in-one installation](https://concoursetutorial.com/#getting-started)

```
curl -O https://raw.githubusercontent.com/starkandwayne/concourse-tutorial/master/docker-compose.yml
docker-compose up -d
```

The Concourse CI web interface is available at: http://127.0.0.1:8080/


Github integration
------------------
[Documentation](https://concourse-ci.org/install.html#github-auth-config)

Add these parameters to concourse docker image as environment variables. Use
the appropriate github client_id and secret.
```
    - CONCOURSE_MAIN_TEAM_GITHUB_TEAM=${GITHUB_TEAM}
    - CONCOURSE_GITHUB_CLIENT_ID=${GITHUB_CLIENT_ID}
    - CONCOURSE_GITHUB_CLIENT_SECRET=${GITHUB_CLIENT_SECRET}
```

Save target and auth information:
```
fly -t test login -c http://127.0.0.1:8080 -u <github_user>
```

Additional github groups:
```
fly -t test set-team --team-name=sustaining --github-team=hortonworks:sustaining
fly -t test set-team --team-name=Hortonworkers --github-team=hortonworks:Hortonworkers
fly -t test teams
```
