# DataAI ETL for Oracle AIDP Spark â€” Customer-Ready Evaluation

This public repository distributes the customer-ready **Oracle AIDP Spark** evaluation package from Yanbor LLC, provider of the DataAI product. DataAI ETL runs as libraries and integration assets inside the customer's pipeline; it is not a hosted DataAI service.

DataAI ETL is proprietary, source-available evaluation software built with open-source technologies including Apache Spark. It is **not** open-source software. Read [LICENSE.md](LICENSE.md) before downloading or using the package. The standard evaluation is limited to less than 32 consecutive calendar days, does not authorize production use or redistribution, and is provided **AS IS** with no Yanbor LLC support or service obligation except as expressly agreed in writing.

## Download and verify

- [Customer-ready evaluation ZIP](downloads/DataAI_ETL_Oracle_AIDP_Evaluation.zip)
- [SHA-256 sidecar](downloads/DataAI_ETL_Oracle_AIDP_Evaluation.zip.sha256)
- [Package manifest](manifest.json)
- [Archive contents](PACKAGE_CONTENTS.txt)

Verify the download before extraction:

~~~powershell
$zip = ".\DataAI_ETL_Oracle_AIDP_Evaluation.zip"
$expected = (Get-Content "$zip.sha256").Split()[0].ToLowerInvariant()
$actual = (Get-FileHash $zip -Algorithm SHA256).Hash.ToLowerInvariant()
if ($actual -ne $expected) { throw "DataAI ETL package checksum mismatch." }
~~~

Expected SHA-256: `1eeba40f96e2a3fb67057480715d8978915c7a698eb3a343b91d9b55e4126dab`

## Evaluation workflow

Extract the package, review LICENSE.md, and run the local DataAI Spark smoke test. Upload the included DataAI JARs to a customer-controlled location visible to an isolated Oracle Spark job, configure them through the platform library mechanism or spark-submit --jars, and validate outputs in non-production schemas.

Use only fictional or customer-approved non-production data. A successful smoke test validates the delivered artifacts in the tested environment; it is not production authorization or certification by the third-party platform vendor.

## Documentation

1. [Check and install the Windows prerequisites](DataAIETLPrerequisites.html).
2. [Follow the product installation guide](docs/INSTALLATION_GUIDE.html).
3. [Use the product usage guide after installation](docs/USAGE_GUIDE.html).
4. [Review the product evaluation-license page](docs/EVALUATION_LICENSE.html).
5. [Review the complete DataAI ETL function catalog](docs/FUNCTION_CATALOG.html), including matrix balancing.

Additional adapter documentation is included in `docs/` for IRIS and Tableau function outputs and schemas.

## Repository contents

```text
README.md
LICENSE.md
COMMERCIAL_LICENSE_TEMPLATE.md
DataAIETLPrerequisites.html
PACKAGE_CONTENTS.txt
SHA256SUMS.txt
manifest.json
downloads/
  DataAI_ETL_Oracle_AIDP_Evaluation.zip
  DataAI_ETL_Oracle_AIDP_Evaluation.zip.sha256
docs/
  INSTALLATION_GUIDE.html
  USAGE_GUIDE.html
  EVALUATION_LICENSE.html
  FUNCTION_CATALOG.html
  adapter output documentation
  usage.css
```

The ZIP contains the complete customer-facing evaluation layout, its own license, internal SHA-256 manifest, samples, documentation, platform assets, DataAI libraries, and executable smoke-test path for this integration. Java, Spark, Hadoop, vendor platforms, BI applications, orchestration products, proprietary drivers, cloud accounts, credentials, and customer infrastructure are not supplied unless the package expressly says otherwise.

The source catalog row is published at [DataAI ETL Markets](https://oureports.net/OUReports/DataAIETLmarkets.html). Commercial or production rights require a separate written agreement, order form, or license certificate from Yanbor LLC.