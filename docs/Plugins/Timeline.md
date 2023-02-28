# Timeline

The [Timeline plugin](https://omeka.org/classic/plugins/Timeline/){target=_blank} allows you to add items to a timeline in your Omeka Classic site. Timelines can be displayed in pages using shortcodes, or as part of exhibits using the [Exhibit Builder plugin](ExhibitBuilder.md#additional-layouts).

Timeline dates and intervals must be in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601){target=_blank} format (`YYYY-MM-DDThh:mm:ss`), with a `/` separator between interval beginnings and ends. If date/interval values are not formatted correctly, the item will be left out of the timeline. 

If an item has multiple date values or interval values, the Timeline plugin will accept the first properly formatted value (so, if you have textual dates such as "circa 1850" or "16??" Timeline will ignore these in favor of a numerical value).
If an item has both a discrete date value and interval value in the fields mapped by timeline metadata, the interval value will take precedence over the date value. An item with an interval does not need to have a date value in this case. 

## Creating a timeline

Once you have installed and activated the Timeline plugin, Timeline should appear in the left navigation bar. Clicking on it will take you to the Browse Timelines page.

To create a timeline, click the "Add a Timeline" link. 

![Link to add timeline](../doc_files/plugin_images/timeline_add.png)

On the Add a Timeline page, enter the following metadata:
- Title: the name of your timeline, which will be displayed to users
- Description: an introduction or overview for the timeline
- Item Date: a dropdown to select the metadata field to use for item date containing discrete time/date values
- Item Interval: a dropdown to select the metadata field to use for item date containing time/date span values (must use a `/` separator between two ISO 8601 formatted dates)
- Item Title: a dropdown to select the metadata field to use for item titles
- Item Description: a dropdown to select the metadata field to use for item descriptions
- Status: a dropdown to select whether the timeline is public or not public
- Featured: a dropdown to select whether the timeline is featured or not featured.

Once you have entered the metadata, click "Save Changes" to create your timeline. If your timeline was sucessfully saved, you will be returned to the Browse Timelines page and your new timeline will now be listed there. If you would like to change the metadata for your timeline, click "Edit Metadata".

![Existing timelines listed on browse timeline page](../doc_files/plugin_images/timeline_browse.png)

## Adding items

Your timeline will appear empty until you populate it. To add items to your timeline, click "Edit Item Query".

![Search options for editing item query](../doc_files/plugin_images/timeline_query.png)

On the edit page, you can add items via the following fields:
 - Search for Keywords
 - Narrow by Specific Fields
 - Search by a range of ID#s
 - Search by Collection
 - Search by Type
 - Search by User
 - Search by Tags
 - Public/Non-Public
 - Featured/Non-Featured
 - Search by Exhibit
 - Item Relations.

You can add items using one or any combination of these fields. For instance, if you know that the majority of the content for the timeline is contained in a single exibit you would want to select that exhibit in the corresponding dropdown. If you wanted to be sure you did not miss any relevant items that were not included in that exhibit, you may want to use the "Specific Fields" search to include any items mentioning the topic in their metadata that are not part of that exhibit. Or, you may want to search by a specific user if you only want to include that person's work. By adjusting the fields you can expand or narrow the scope of items included on your timeline.

Once you have filled in all the desired search fields, click "Search for Items". This will add all relevant items to your timeline.

![Timeline populated based on query](../doc_files/plugin_images/timeline_populated.png)

To further add or remove items from your timeline, you can adjust you query by clicking "Edit Item Query". If you click "Delete", you will delete the entire timeline and its metadata. To see the public view of your timeline, click "View Public Page".

### Value formatting

You may need to manually edit some date or interval values to include items on your timeline to match [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601){target=_blank} formats. 

Use the following formats for [dates](https://en.wikipedia.org/wiki/ISO_8601#Dates){target=_blank}, including dashes between values:

- `2022`
- `2022-08` (year and month, no date)
- `2022-08-18`.

Use the following formats to add [times](https://en.wikipedia.org/wiki/ISO_8601#Times){target=_blank} to your date values:

- `2022-08-18T17:26:49+00:00` ([time offset from UTC](https://en.wikipedia.org/wiki/ISO_8601#Time_offsets_from_UTC){target=_blank})
- `2022-08-18T17:26:49Z` ([coordinated universal time](https://en.wikipedia.org/wiki/ISO_8601#Coordinated_Universal_Time_(UTC)){target=_blank}). 

You cannot omit the year while providing a month and/or day. You cannot supply ordinal dates (as in, `2000-175` for the 175th day of the year 2000). 

Use the following formats for [intervals](https://en.wikipedia.org/wiki/ISO_8601#Time_intervals){target=_blank} with start and end points. 

- `2007/2008`
- `2007-03/2008-05` (Will appear in the timeline as "March 2007 - May 2008")
- `2007-03-01T13:00:00Z/2008-05-11T15:30:00Z` (Will appear in the timeline as "1 March 2007 13:00:00 +00:00 — 11 May 2008 15:30:00 +00:00").

You cannot supply a [duration](https://en.wikipedia.org/wiki/ISO_8601#Durations){target=_blank} value.

## Displaying your timeline

There are several different methods you can use to view and/or display your timeline. Timeline integrates with the [Exhibit Builder plugin](ExhibitBuilder.md#additional-layouts) by adding a new Timeline block option to exhibit pages: 

![Admin view of timeline option in exhibit builder](../doc_files/plugin_images/timeline_eb.png)

You can also add a timeline to a page using [Shortcodes](../Content/Shortcodes.md). 