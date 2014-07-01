# Barton

> No one, however smart, however well educated, however experienced, is the suppository of all wisdom.
>
> -- Tony Abbott, Prime Minister of Australia [12 Aug 2013](http://www.smh.com.au/federal-politics/federal-election-2013/liberals-squirm-as-abbott-refers-to-the-suppository-of-wisdom-20130812-2rryy.html)

Barton is a ~~suppository~~ repository of political wisdom.  More specifically though, it's a structured collection of crowd sourced contact details for all elected officials in Australia, designed for consumption by APIs and apps.

Despite the interwebs being around for over 20 years, a complete database of Australian politician contact details still doesn't exist.  Many government websites already provide data as `mail-merge.docx` or `contact-details.pdf` for download.  Unfortunately, none of them use a consistent structure or format suitable for automated consumption.

Barton seeks to rectify this problem.

## File Structure

The repo is a simple collection of [YAML files](http://www.yaml.org/spec/1.2/spec.html).  Each YAML file in the `data/` directory represents the jurisdiction of a single political authority.   

The following data conventions will serve as the public API.

- `Files` MUST start with 3 dashes `---`.
- `Files` MUST only contain a single jurisdiction of political authority.
- `Files` SHOULD be named descriptively so that jurisdictions will group appropriately by the file system i.e. `au-qld-local-brisbane-city-council.yaml`  
- `Files` MUST contain a `name` field.  Files MAY contain `tags` and `people` collections.
- `Tags` MUST contain a collection of strings which SHOULD apply to the current element and all of its children.

    
```    
    ---
    name: People's Democratic Banana Republic
    tags: [tags are strings, they apply to this, and all children]
    people: 
      - name: Barry Crocker
``` 
    
- `People` MUST be a collection.
- `People` elements MUST contain a `name` field, as well as `roles` and `contact` collections.
- `People` elements MAY contain any other fields as required, including `title`, `tags`, `salutation`, `suffix`, `party`.
- `Name` fields are strings with the format `First [Middle] ['Preferred'] Lastnames`
- `Contact` collections MUST contain at least one `office` elements. 

```    
      - name: Barry 'Bazza' Crocker
        roles:
         - Minister for Political Entitlements
         - Member for Woolloomooloo
        contact:
         - office: Electorate
           address: Corner Cowper Wharf Roadway & Brougham Road, Woolloomooloo, NSW 2011
           postal: PO Box 122, Sydney NSW 2001
           email: bazza@parliament.nsw.gov.au
           phone: 02 9357 3074
           fax: (02) 9357 3020
           web: http://www.barrycrocker.com.au
           facebook: http://facebook.com/barrycrocker69
        party: LNP
        title: The Right Honourable
        salutation: Dear Minister
        suffix: MP
        tags: [Pies & Mash, Gravy, Schooners]
``` 

Putting it all together yields something like:

    ---
    name: Queensland Government
    tags: [Queensland, state]
    people: 
      - name: Verity Mary Barton
        salutation: Dear Miss
        suffix: MP
        roles:
         - Member for Broadwater
        party: LNP
        contact:
         - office: Electorate
           address: 102 Imperial Parade, (Cnr Government Rd and Imperial Pde), Labrador Qld  4215
           postal: PO Box 644, Labrador Qld 4215
           email: broadwater@parliament.qld.gov.au
           phone: 07 5563 9010
           fax: 07 5500 5364
      - name: Campbell Kevin 'Can Do' Newman
        title: The Honourable
        salutation: Dear Premier    
        suffix: MP
        roles:
          - Premier of Queensland
          - Member for Ashgrove
        party: LNP
        contact:
          - office: Ministerial
            address: Level 15, Executive Building, 100 George Street, Brisbane Qld 4000
            postal: PO Box 15185, City East Qld 4002
            email: thepremier@premiers.qld.gov.au Shop 2, 230 Waterworks Road, Ashgrove Qld 4060
            phone: 07 3719 7000
            fax: 07 3220 6222        
          - office: Electorate
            postal: PO Box 3010, Ashgrove East Qld 4060
            email: ashgrove@parliament.qld.gov.au
            phone: 07 3366 6000
            fax: 07 3366 6202
   
## Usage

To access the most up-to-date politician contact details, simply clone, curl, or scrape the repo.  Parse the YAML into your preferred data format and use it to find a politician, write to your representative, or start a revolution - implementation is up to you. 

## Contributing

Barton is a collective endeavour that needs your assistance.  You can help out anytime by adding or updating the contact details for officials in your local electorate or further afield.  Please see the [contributing](contributing.md) file for how to help out.

## Internationalisation

Want to create a similar database for your own country? Sweet - just copy this readme into a repo named after your first Head of Government and you are away!

## License

Barton is licensed under a [Creative Commons Attribution 3.0 Australia](http://creativecommons.org/licenses/by/3.0/au/deed.en) License.  You are free to share and adapt the material for any purpose, even commercially so long as you give appropriate credit in your source code, website, or publication.