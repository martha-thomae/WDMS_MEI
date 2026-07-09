# README

## Instructions for connecting the encoded music to the facsimile image
Edits to make the MEI files, which include the music of the selected source, link to the facsimile images in this repository:
1. Add a `<facsimile>` element as child of `<music>`
2. This `<facsimile>` element must have the following structure:
   ```xml
   <facsimile>
     <surface xml:id="surface001">
       <graphic target="https://raw.githubusercontent.com/martha-thomae/WDMS_MEI/refs/heads/main/Image27.jpg"/>
     </surface>
   </facsimile>
   ```
   It is important that the `<surface>` element has an `@xml:id` (as it will be referenced later in the file). Also, the `@target` in `graphic` should contain the link to the selected image in this repository (the image corresponding to the music contents in the MEI file).
3. Then, add a `<pb>` element as a child of `<section>`, this `pb` should have a `@facs` attribute that points to the `xml:id` of `<surface>`. For example, based on the encoding shown in _item 2_, the `pb` element should be:
   ```xml
   <pb facs="#surface001"/>
   ```
   Remember that to make a reference to an id, one needs to use the `#` sign.

To see a complete example of a file including these changes, see [example.mei](./example.mei)

Once these edits are done, if the file is uploaded to [_mei-friend_](https://mei-friend.mdw.ac.at), and the check box of "Full page" is selected in the facsimile panel, the image will show up. 
Then one can use the "Edit zones" check box to draw bounding boxes for each of the symbols and connect them to the righ symbols in the encoded music. To do this:
1. Check the "Edit zones" checkbox
2. Click on the symbol (e.g., the note or rest) for which you want to indicate their positioning in the facsimile
3. Draw a bounding box on the image for that symbol
