Plugins/OaipmhHarvester
=======================


[Plugins](../Plugins.1.html "Plugins")

The OAI-PMH Harvester plugin imports records from OAI-PMH data
providers.

Some online repositories expose their metadata through the [Open Archives Initiative Protocol for Metadata Harvesting](http://www.openarchives.org/pmh/) (OAI-PMH). This plugin makes it possible to harvest that metadata, mapping it to the Omeka data
model. The plugin can be used for one-time data transfers, or to keep
up-to-date with changes to an online repository.

Currently the plugin is able to import [Dublin Core](http://dublincore.org/documents/dces/) and [CDWA Lite](http://www.getty.edu/research/conducting_research/standards/cdwa/cdwalite.html)
metadata. Dublin Core is an internationally recognized standard for
describing any resource. Every OAI-PMH data provider should implement
this standard. CDWA Lite is a standard for describing works of art and
material culture. Very few repositories expose CDWA Lite, but the
standard is getting more and more popular.

Omeka has plans to translate more metadata formats, such as
[MARCXML](http://www.loc.gov/standards/marcxml/),
[METS](http://www.loc.gov/standards/mets/), and [RFC
1807](http://www.ietf.org/rfc/rfc1807.txt).

Installation 
-----------------------------------------------------------------

If you are using Omeka.net, see [instructions for the plugin on the Help section of Omeka.net](http://info.omeka.net/build-a-website/manage-themes-and-plugins/oai-pmh-harvester/).

1.  Your server must have PHP-CLI 5.2+ installed.
2.  Upload and install the OAI-PMH Harvester plugin (see
    [Installing\_a\_Plugin](https://omeka.org/codex/Installing_a_Plugin "Installing a Plugin"))
3.  Configure the plugin in Omeka (see below)

Configuration 
-------------------------------------------------------------------

-   **Path to PHP-CLI**: Path to your server's PHP-CLI command. The PHP
    version must correspond to normal Omeka requirements. Some web hosts
    use PHP 4.x for their default PHP-CLI, but many provide an
    alternative path to a PHP-CLI 5 binary. Check with your web host for
    more information.
-   **Memory Limit**: Set a memory limit to avoid memory allocation
    errors during harvesting. We recommend that you choose a high
    memory limit. Examples include 128M, 1G, and -1. The available
    options are K (for Kilobytes), M (for Megabytes) and G
    (for Gigabytes). Anything else assumes bytes. Set to -1 for an
    infinite limit. Be advised that many web hosts set a maximum memory
    limit, so this setting may be ignored if it exceeds the maximum
    allowable limit. Check with your web host for more information.

Upgrading 
-----------------------------------------------------------

The data stored by the harvester plugin has changed between versions, so
when upgrading, it is necessary to uninstall the old version of the
plugin first. This will remove data stored by the harvester, but the
harvested items themselves will remain.

To upgrade the plugin:

1.  Uninstall the old version of the OAI-PMH Harvester plugin from the
    admin panel.
2.  Replace the OaipmhHarvester directory with the updated version.
3.  Install the now-updated OAI-PMH Harvester plugin from the
    admin panel.

Instructions 
-----------------------------------------------------------------

### Performing a harvest

1.  Go to Admin &gt; "OAI-PMH Harvester"
2.  Enter an OAI-PMH base URL, click "View Sets"
3.  Select a set and the metadata prefix to harvest, click "Go"
4.  The harvest process runs in the background and may take a while
5.  Go to the harvest's "Status" page to check the progress
6.  If you encounter errors, submit the base URL and status messages to
    the Omeka forums

-   Try out plugin using [harvestable Omeka OAI sets](https://omeka.org/codex/Harvestable_Omeka_OAI_sets "Harvestable Omeka OAI sets").

### Re-harvesting and updating 

The harvester includes the ability to make multiple successive harvests
from a single repository, keeping in sync with changes to that
repository.

After a repository or set has been successfully harvested, a
"Re-harvest" button will be added to its entry on the Admin &gt; OAI-PMH
Harvester page. Clicking this button will harvest from that repository
again using all the same settings, adding new items and updating
previously-harvested items as necessary.

Manually specifying the exact same harvest to be run again (same base
URL, set, and metadata prefix) will result in the same behavior.

### Aborting a harvest 

A harvest in progress can be aborted by clicking the "Kill Process"
button in the harvest's entry on the Admin &gt; OAI-PMH Harvester page.
The harvest will immediately be aborted. Alternatively, the PID of the
background process is displayed for currently-running harvests, and this
can be used to manually kill or pause the process.

### Duplicate items 

Duplicate items (multiple Omeka items corresponding to the same
repository record) can be created if an item in a repository is a member
of several OAI-PMH sets. This will also occur if a repository is
harvested using more than one metadata prefix. In this case, the
duplicate items are idependent, and changes to one will not propagate to
the others.

However, the duplicate items, if any, can be accessed from the admin
item show page. If an item has duplicates, they will be shown in an
infobox on the right-hand side of the page titled "Duplicate Harvested
Items."

