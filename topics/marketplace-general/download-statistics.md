[//]: # (title: Download statistics)


<note>
    <p>Recently, the procedure to count downloads has been reworked, so you might see some differences between your previous download number and the new one. The old processing considered any connection to CDN as a full download, even if the user never actually received anything (errors, for example), while this new algorithm counts only successful downloads.</p>
</note>
<p>Download growth is a key performance indicator for your plugin. You can view the plugin downloads statistics on the Overview page of your plugin. Filter out downloads by the specific plugin version or view the overall statistics for all stable versions released.</p>
<p>Additionally, you can view downloads divided by period (month, week, day) or specific IDE (without a time reference). You can download the graph in various formats (image, CSV, etc.)</p>
<p>Plugin download statistics for all versions may also include downloads of removed updates. Keep in mind that the processing latency for download statistics is 24 hours.</p>

### Total Downloads:

<warning>
    <p>We have stopped counting the total number of unique downloads, at least for now. However, you can still check the number of unique downloads per day, per week, or per month. We may start displaying the total again if we can identify the best way to measure it.</p>
</warning>

<p>We show the total number of downloads right above the graph. This number is also displayed in the plugin card preview and IDE search.</p>

<img src="download-main.png" alt="Main Download Window"
width="720"/>

### Unique Downloads:

<p>By default, we show unique download statistics.</p> 
<p>The uniqueness is based on the unique user ID (UUID)  which is bound to the computer OS. The UUID is shared among all IntelliJ-based IDEs on this computer and does not change during IDE updates.However, the UUID will be different if an IDE with one license is installed on various computers.</p>

### Downloads by version:

<p>When <code>All Versions</code> mode is selected, the plugin version is ignored during calculation.</p>
<p>For example, downloads of version 1.1 and version 1.2  with the same UUID will be non-unique.</p>

### Downloads by timeframes:

<p>If there are several downloads by one UUID within one week, this will be counted as one unique download in the weekly and monthly views.</p>

<img src="unique-download.png" alt="Downloads filtered by timeframes"
width="720"/>



