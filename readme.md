# Barton

> No one, however smart, however well educated, however experienced, is the suppository of all wisdom.
>
> -- Tony Abbott, Prime Minister of Australia [12 Aug 2013](http://www.smh.com.au/federal-politics/federal-election-2013/liberals-squirm-as-abbott-refers-to-the-suppository-of-wisdom-20130812-2rryy.html)

Barton is a ~~suppository~~ repository of political wisdom.  More specifically though, it's a structured collection of crowd sourced contact details for all elected officials in Australia, designed for future consumption by APIs and apps.


## File Structure

The repo is a simple collection of [YAML files](http://www.yaml.org/spec/1.2/spec.html).  Each YAML file in the `data/` directory represents the jurisdiction of a single political authority.  Files are named descriptively so that jurisdictions will group appropriately by the file system i.e. `au-local-qld-brisbane-city-council.yaml`  

The following data conventions will serve as the public API.

- Each file MUST contain a single jurisdiction of political authority with at most one level of partitions and associated people.
- Each jurisdiction MUST contain a `name` entity.  Jurisdictions MAY contain `tags`, `people`, and `partitions` entities.  
- `Partitions` MUST contain `name`, `type`, and `people` entities.  Partitions MAY contain a `tags` entity.
- `People` MUST contain a `name` and `role` entity.  People MAY contain any other fields as required.
- `Tags` MUST contain a sequence of strings meant to apply to an element and all of its children.

The _one jurisdiction per file_ and _at most one partition_ rules means that some levels of government will have multiple files ie the Queensland Government, having a unicameral parliament, needs only one file while the Government of Victoria requires three - one for the Cabinet & Executive, one for the Legislative Assembly, and one for the Legislative Council.

This is what the local government area of Brisbane City Council would look like:

    ---
    name: City of Brisbane
    tags: [LGA, local, South East Queensland]
    people:
      - name: Graham Quirk
        role: Lord Mayor
        title: The Right Honourable
        salutation: My dear Lord Mayor
        post: Office of the Lord Mayor, GPO Box 2287, Brisbane Qld 4001
        phone: 07 3403 4400
        fax: 07 3403 9930
    partitions:
      - name: Bracken Ridge
        type: Ward
        people:
          - name: Amanda Cooper
            role: Councillor
            postal: Cnr Bracken and Barrett Streets, Bracken Ridge Qld 4017
            phone: 07 3667 6000
            fax: 07 3667 6005
            email: brackenridge.ward@ecn.net.au
            web: www.amandacooper.com.au
      - name: Central
        type: Ward
        people:
          - name: Vicki Howard
            role: Councillor
            postal: Shop 11, 31 Duncan Street, Fortitude Valley Qld 4006
            phone: 07 3403 0254
            fax: 07 3403 0256
            email: central.ward@ecn.net.au

## Usage

To access the most up-to-date politician contact details, simply clone, curl, or scrape the repo.  Parse the YAML into your preferred data format and use it to find a politician, write to your representative, or start a revolution - implementation is up to you. 

## Contributing

Barton is a collective endeavour that needs your assistance.  You can help out anytime by adding or updating the contact details for officials in your local electorate or further afield.  Please see the [contributing](contributing.md) file for how to help out.

## Internationalisation

Want to create a similar database for your own country? Sweet - just copy this readme into a repo named after your first Head of Government and you are away!

## License

Barton is licensed under a [Creative Commons Attribution 3.0 Australia](http://creativecommons.org/licenses/by/3.0/au/deed.en) License.  You are free to share and adapt the material for any purpose, even commercially so long as you give appropriate credit in your source code, website, or publication.