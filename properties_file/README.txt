How to translate launchpad site content: 
---------------------------------------

1.EXTRACT CONTENT TO TRANSLATE FROM ZIP FILES:
	After you have downloaded the translations zip file, extract the source file that contains the site's source strings: <SiteId>.properties.
	For example: 4c736e0c-a094-46f1-9ae5-a602eb23b2b9.properties.
	Then, extract the site's assets, located under the ASSETS folder. The assets are files such as images, documents, videos, and text files.

2.TRANSLATE SITE PROPERTIES FILE:
	The content of the source file <SiteId>.properties is in the following format: <key> = <value>

	<key> = Property key. Do not change it.
	<value> = String to translate.

	Save another copy of the source file and translate all the property values.
	Non-translated properties will display the strings of the source site.
	
3.SAVE TRANSLATED SITE PROPERTIES FILE:
	 After you have finished translating the strings for a locale (language-country), rename the properties file using the following naming convention:

	<SiteId>_<Language>-<Country>.properties
	or
	<SiteId>_<Language>.properties

	<Language> should be according to the ISO 639 convention.
	<Country>  should be according to the ISO 3166 convention.

	Examples: 
		4c736e0c-a094-46f1-9ae5-a602eb23b2b9_en-US.properties
		4c736e0c-a094-46f1-9ae5-a602eb23b2b9_en.properties

4.MULTIPLE TRANSLATIONS (OPTIONAL):
	You can repeat steps 2-3 for additional languages.
	Each language must be in a separate properties file. The file names differ by the locale suffix.

	Examples:
	4c736e0c-a094-46f1-9ae5-a602eb23b2b9_en-US.properties
	4c736e0c-a094-46f1-9ae5-a602eb23b2b9_de-DE.properties

5.TRANSLATE SITE ASSETS:
	Translate each asset to the required languages, and rename each asset file by adding the corresponding locale (language-country) to the file name using the following convention:	

	<asset name>_<Language>-<Country>[.<extension>]
	or
	<asset name>_<Language>[.<extension>]

	Examples:
	MyImage_de-DE.jpg
	MyDoc_de.txt
	MyImage_fr-FR.jpg
	MyDoc_fr.txt

6.COMPRESS TRANSLATED FILES:
	Compress all the translated files into a new zip file, where the translated assets are located under a folder named ASSETS.
	For example:

	<SiteId>_en.properties
	<SiteId>_de.properties
	<SiteId>_fr.properties
	ASSETS
		MyImage_en.jpg
		MyImage_de.jpg
		MyImage_fr.jpg
	
	The name of the zip file is not important.

7.UPLOAD ZIP:
	Open the launchpad site and upload the new zip file using the "Manage Translations" editor.


#Important guidelines:
���       An uploaded zip file can contain translations for one site only.
���       The content of a translation file must be according to the format described in step 2 (<key> = <value>).
���       The name of a translated properties file must be according to the convention described in step 3 (<SiteId>_<Language>-<Country>.properties).
���       The name of a translated asset file must be according to the convention described in step 5 (<asset name>_<Language>-<Country>[.<extension]).
���       The translated asset files must be in a folder named ASSETS.
���       The runtime locale is determined by a parameter in the URL (sap-language=<locale>), or by the browser settings if there is no parameter in the URL.
���       The translation uses one of the following, in order of precedence:
	* <SiteId>_<Language>-<Country>.properties	or	<asset name>_<Language>-<Country>[.<extension>]
	* <SiteId>_<Language>.properties		or	<asset name>_<Language>[.<extension>]
	* <SiteId>_en.properties			or	<asset name>_en[.<extension>]
	* Site's source strings				or	Asset's source strings
	It is recommended to have a translation to English (<SiteId>_en.properties or <asset name>_en[.<extension>]) as a fallback, instead of using the site's source strings.
