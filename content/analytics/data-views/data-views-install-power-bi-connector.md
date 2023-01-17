---
uid: data-views-install-power-bi-connector
---

# Power BI Connector

The AVEVA Data Hub Power BI Connector retrieves Data Views from AVEVA Data Hub and makes them available in Microsoft Power BI for advanced data visualization and analysis. Install AVEVA Data Hub Power BI Connector to retrieve Data Views for use with Microsoft Power BI as described in this section.

## System requirements

The following are required before you install and use AVEVA Data Hub Power BI Connector.

- Operation Systems: Windows 10, Windows Server 2012 R2, Windows 8.1, Windows Server 2016, Windows Server 2019

- For desktop installation: Microsoft Power BI Desktop 2.91.884.0 or later

- For on-premises Data Gateway installation: Microsoft Power BI On-premises Data Gateway 3000.89.6 or later

- Microsoft Edge WebView 2 Runtime

- A user account with Administrator privileges to install AVEVA Data Hub Power BI Connector on a local machine.

## Install AVEVA Data Hub Power BI Connector

To install the AVEVA Data Hub Power BI Connector:

1. In the left pane, select **Analytics** > **Data Views**.

1. Select any data view.

1. Select **Edit Data View**.

1. Download the `AVEVADataHubPowerBIConnector.exe` file by selecting the AVEVA Data Hub Power BI Connector banner.

1. Install AVEVA Data Hub Power BI Connector by either the setup wizard or silent installation.

    - Setup wizard

        - Double-click the `AVEVADataHubPowerBIConnector.exe` file and select **Next**.

        - (Optional) To install the connector to an on-premises data gateway, select `On-premises data gateway installation` and enter the directory where you want to install the connector.

    - Silent installation

        - Open a command prompt window and type following command:

        `.\AVEVADataHubPowerBIConnector.exe -Y INSTALLDIR="<install path>" /quiet`

             **Note:** AVEVA Data Hub Power BI Connector supports silent installation for on-premises data gateway installations.