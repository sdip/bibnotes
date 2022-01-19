# Changelog

All notable changes to this project will be documented in this file.  

## [0.8.13] 

### Improvement
- Instead of automatically exporting the extracted annotation at the end of the note, the position in the note can be defined in the template using the placeholder {{PDFNotes}}. This is a breaking change from the previous version. In order to retain the same output as in the previous versions, add "## Extracted Annotations" followed by "{{PDFNotes}}" in the custom template.
- In addition to extracting all the highlights/comments in a sequential order, it is also possible to extract groups of highlights based on the highlight colour using the following placeholder:
    - {{Yellow}}
    - {{Red}}
    - {{Green}}
    - {{Black}
    - {{White}}
    - {{Gray}}
    - {{Cyan}}
    - {{Magenta}}
    - {{Orange}}
- Added capacity to export notes stored within Zotero that have been generated manually rather than exported from the pdf. The position in the text can be defined by adding to the template the placeholder {{UserNotes}}
- Added capacity to import images that are extracted from the PDF using the Zotero native pdf Reader. In the settings, you can select whether to link to the image that is stored in the Zotero main folder or copy this image inside your Obsidian vault, and the location. Comments made on an image can be placed above or below the image inside the note by changing the setting. It is also possible to extract the images in a specific location of the note adding the placeholder {{Images}} in the template.
- Added new setting to decide whether 1) updating an existing note will over-write the existing note completely ("Overwrite Entire Note"), only add non-overlapping sentences ("Save Entire Note"), or adding non-overlapping sentences in a specific section, while over-writing the rest (""Select Section"). The ""Select Section" is chosen, the plugin will ask for a string identifying the beginning and/or end of the section to be updated (rather than overwritten). 
If the "start" field is left empty, the existing text will be preserved from to the beginning of the note. If the "end" field is left empty, the existing text will be preserved until  the end of the note. For instance, in order to over-write the metadata but maintain changes made manually to the extracted annotations, the start of the section to be preserved should be set to the unique title used in the template before the metadata (e.g. "## Extracted Annotations").
- Added suggester field in the settings to select the folder to export the note (credit to Templater plugin and Periodic Notes Plugin.)
- Added settings to control whether updating an existing slide will overwrite the changes made manually within Obsidian or preserve them (default)
- Create new setting that allows you to control whether when launching the "Update Library" modal, the plugin will only update existing notes or also create new notes that are missing from the local library
- Added settings to manually input the character dividing multiple authors, editors, tags, or collections
- Introduced the possibility of wrapping fields with multiple values (authors, editors, keywords, collections) in quotation marks (e.g. by adding "{{author}}" in the template)
- Introduced the possibility of adding a tag(#) in front of  fields with multiple values (authors, editors, keywords, collections). For instance,  adding #{{keywordsZotero}} in the template will result in #Keyword1, #Keyword2
- Introduced three different template fields to add to your note the keywords/tags extracted by zotero ({{keywordsZotero}}), the tags/keywords extracted from the PDF ({{keywordsPDF}}), and both sets of keywords/tags ({{keywords}} or {{keywordsAll}
- Introduced the setting to control the format of the in-line reference at the end of a highlight extracted from the PDF. Three default options are provided: "Author, year, page number", "Only page number", "Empty"
- Introduced the setting to control whether to include next to each extracted highlight, comment, and figure a link opening within the Zotero reader the page of the pdf file where this element is extracted from.
 

### Debugging
- Fixed bug where the code exporting notes did not allow for underscores and other non-alphanumeric characters in the title of the exported notes
- Fixed bug in the function creating tasks when both a comment and a highlight are present.
- Move the cursor to the search bar when launching the "Create/Update Literature Note" command
- Changes to the json file exported by Zotero are ready by Obsidian without having to restart the application

 