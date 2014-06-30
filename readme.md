# Barton

> No one, however smart, however well educated, however experienced, is the suppository of all wisdom.
>
> -- Tony Abbott, Prime Minister of Australia [12 Aug 2013](http://www.smh.com.au/federal-politics/federal-election-2013/liberals-squirm-as-abbott-refers-to-the-suppository-of-wisdom-20130812-2rryy.html)

Barton is a ~~suppository~~ repository of political wisdom.  More specifically though, it's a structured collection of contact details for all elected officials in Australia, designed for future consumption by APIs and apps.


## File Structure

The repo is a simple collection of [YAML files](http://www.yaml.org/spec/1.2/spec.html).  Each YAML file represents the jurisdiction of a single political authority.  Files are named descriptively so that jurisdictions will group appropriately by the file system i.e. `au-local-qld-brisbane-city-council.yaml`  Thus the abstract structure will look like:

 The following data conventions will serve as the public API.

- Each file MUST contain a single jurisdiction of political authority with at most one level of partitions and associated people.
- Each jurisdiction MUST contain a `name` entity.  Jurisdiction MAY contain `tags`, `people`, and `partitions` entities.  
- `Partitions` MUST contain `name`, `type`, and `people` entities.  Partitions MAY contain a `tags` entity.
- `People` MUST contain a `name` and `role` entity.  People MAY contain any other fields as required.
- `Tags` MUST contain a sequence of strings meant to apply to an element and all of its children.

Example....

## Usage

To access the most up-to-date politician contact details, simply clone, curl, or scrape the repo.  Parse the YAML into your preferred data format and use it to find a politician, write to your representative, or start a revolution - implementation is up to you. 

## Contributing

Assistance is very welcome.  New elections will require updated information so please muck in using the following workflow:

1. Open an issue stating which jurisdiction you want to update.
2. Fork the repo and create an appropriately named branch e.g. `au-local-brisbane`.
3. Update the jurisdiction's contact details.
4. Submit a [pull request](https://help.github.com/articles/creating-a-pull-request).
5. Pour a cup of tea, enjoy a bickie and reflect on your good work.

To find out how to add or update data, have a look at the [contributing](contributing.md) file.

## Internationalisation

Want to create a similar database for your own country? Sweet - just copy this readme into a repo named after your first Head of Government and you are away!

## License

Barton is licensed under a [Creative Commons Attribution 3.0 Australia](http://creativecommons.org/licenses/by/3.0/au/deed.en) License.  You are free to share and adapt the material for any purpose, even commercially so long as you give appropriate credit in your source code, website, or publication.