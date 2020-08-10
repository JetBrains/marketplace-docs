[//]: # (title: Unique Downloads)

## Uniqueness

Uniqueness is based on an UUID which is bounded to an OS user on a computer. The UUID is shared between all IntelliJ-based IDEs on this computer. The UUID doesn't change during IDEs updates.
However, the UUID will be different if an IDE with one license is installed on various computers.

## Examples

If the **"All Versions"** mode is selected (as shown in the figure below) then the plugin version is ignored during statistic calculation. E.g., the downloads of version 1.1 and version 1.2 with the UUID=123 are non-unique.

![All Versions](all_versions.png)

If there are several downloads with one UUID in different timeframes then in each timeframe there will be one unique download. E.g., the daily statistic has several downloads with UUID=123 in July and August. This will be counted as 1 unique download in July and 1 in August.

![Unique Daily](unique_daily.png)

![Unique Monthly](unique_monthly.png)
