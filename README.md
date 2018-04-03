# Tesseract

Olap hypercube server.
Not designed for production use.

## Design
Front-end: Http api only, no mdx. Follows mondrian-rest
Back-end: Connects to (and generates sql for) Postgres or Monet
Olap:
  - sql generator
  - caching (cubes) (someday)
  - results formatter (json, jsonrecords, csv)

## API

### Describe (REST api convention)

`<base_url>/``cubes/<cube>/dimensions/<dimension>/hierarchies/<hierarchy>/levels/<level>/members`

Putting in an id will give specific instance, otherwise leaving out id will give a list.


### Aggregate
`<base_url>/``cubes/<cube>/aggregate.<format>?<aggregation_query_params>`: aggregate using query params

### Analytics
`unimplemented!();`

## Stack

Rocket for web api (easy to use sync interface)
Diesel for ORM (easy to use sync interface with good escape hatch)

Consider actix-web instead of rocket if want stable
