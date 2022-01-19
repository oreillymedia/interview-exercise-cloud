# interview-exercise-cloud

The O'Reilly search API provides information on the many books which are available on our Learning Platform. Your assignment is to develop a REST API in either Python or GoLang. The API should include endpoints that allow users to get information on all of the books it has stored, a subset of these books and a single book. We would also like you to provide an endpoint through which users can add more books to your API. A PostgreSQL container image with an initial data set has been provided in the instructions below.

Finally, containerize your application as if you were deploying it to a Kubernetes cluster.

## Database

### Setup

We have provided a PostgreSQL container with an initial set of data loaded (200 books). Use this data to create your API endpoints.

To pull this container from DockerHub:
```bash
docker pull registry.hub.docker.com/caedus41/oreilly-cloud-engineer-postgres
```

The credentials for this database is:
```bash
username = oreilly
password = hunter2
```

You can run this container using the following command:
```
docker run --name ormdb -e POSTGRES_PASSWORD=hunter2 -e POSTGRES_USER=oreilly -d registry.hub.docker.com/caedus41/oreilly-cloud-engineer-postgres
```

### Schema Info

All of the data is loaded in the `public` schema within one `works` table. 

The fields in this table are:
```
   Column    |       Type        |
-------------+-------------------+
 work_id     | integer           |
 title       | text              |
 authors     | text              |
 isbn        | character varying |
 description | text              |
 ```
