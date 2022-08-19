[//]: # (title: Plugin Updates)

<chapter title="How to upload an update"
id="update-a-plugin"
level="3"/>

<p>In most cases, updates are uploaded automatically using Gradle tasks as described in <a href="https://plugins.jetbrains.com/docs/intellij/deployment.html">Publishing Plugins with Gradle</a>.</p>
<p>To upload an update manually, just click on the <control>Upload Update</control> button in the top left corner:</p>

<img src="upload-update.png" alt="Upload Update button"
width="706"/>

<note>
  <p>Please verify your plugin update’s compatibility with IDEs by using the built-in <a href="https://blog.jetbrains.com/platform/2018/07/plugins-repository-now-integrates-with-the-plugin-verification-tool/?_ga=2.6528434.1031171388.1644822688-1317262229.1616053452">Plugin Verifier</a> as you upload them. To see all of the options for plugin verification, refer to the <a href="https://plugins.jetbrains.com/docs/intellij/api-changes-list.html#verifying-compatibility">documentation</a>.</p>
</note>

<p>Once the update is successfully uploaded, we will review it to make sure it meets the <a href="https://plugins.jetbrains.com/legal/approval-guidelines">approval criteria</a>. If you have not received a notification about the review status within 2 business days, please contact us at <a href="mailto:marketplace@jetbrains.com">marketplace@jetbrains.com</a> or <a href="https://jetbrains-platform.slack.com/messages/C5U6ZNG20">Slack channel</a>.</p>

<chapter title="How to hide a plugin update"
id="hide-a-plugin-update"
level="3"/>

<p>Once the update is approved, it will be publicly available for download. You can hide this update if there are unexpected issues in the build or for any other reasons. Hidden updates are not available via the Marketplace website or IDE search. Such updates can be reached via direct link only.</p>

<img src="hide-update.png" alt="Hide Update button"
width="406"/>

<p>To make the update publicly available just click on the eye icon again.</p>

<chapter title="How to remove a plugin update"
id="remove-a-plugin-update"
level="3"/>

<p>Plugin version can be easily removed by clicking on the <control>trash can</control> icon:</p>

<img src="remove-update.png" alt="Remove Update button"
width="406"/>

<p>If this icon is not available for this plugin version, it is related to paid or freemium plugins only (specifically, to the <code>release-date</code> parameters). Most likely, there are no other updates with the same  <code>release-date</code> and <code>release-version</code> as in this update, so please consider hiding such version or contact us at <a href="mailto:marketplace@jetbrains.com">marketplace@jetbrains.com</a> with such a request.</p>

<chapter title="How to edit an update after submission"
id="edit-plugin-update"
level="3"/>

<p>There is no option to edit the update after submission except for the compatibility range:</p>

<img src="compatibility-range.png" alt="Edit compatibility range"
width="406"/>

Use `since-build` and `until-build` values to declare the product compatibility of specific version range. Please refer to the following <a href="https://plugins.jetbrains.com/docs/intellij/build-number-ranges.html">build number ranges</a> to specify these values correctly.

<warning><p>Keep in mind that compatibility with the specified version range (and compatible products) must always be verified using <a href="https://plugins.jetbrains.com/docs/intellij/verifying-plugin-compatibility.html#plugin-verifier">Plugin Verifier</a> to ensure binary compatibility.</p></warning>
