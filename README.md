# Lumix Resolve Metadata Importer
Lumix to Davinci Resolve Meta Data import tool allows you to import basic meta data from your lumix video files into Davinci Resolve so that you can see these meta data as you're editing. This is a command line tool, so some mac terminal or windows command line expeirence will be necessary to use this tool.

This tool is a basic wrapper for the wonderful exiftool, which is required to use this.

The following meta data is supported:
* ISO (including whether or not DR boost is on for GH6 and G9II)
* Shutter speed 
* White point (White balance)
* Lens
* Aperture
* Lens focal distance
* Frame rate
* Gamma
* Color space
* Video bit rate
* Audio sample rate
* Audio bit rate
* Camera model
* Camera serial
* Camera firmware
* Camera manufacturer

### Mac OS Installation
* Install exiftool 
    * https://exiftool.org/
    * I strongly recommend installing the windows executable or the MacOS package
* Python 3 is required. Most macs contain this
    * when in doubt you can download a fresh copy from https://www.python.org/downloads/macos/
* Download the zip file containing the script **lumix-to-resolve-main.zip** and extract the zip files
* Open terminal on your Mac
* Change to the directory the contains the unzipped files
* Copy the script to /usr/local/bin using the following commands in terminal (enter your password when prompted)
    * `sudo cp getmetadata /usr/local/bin`
    * `sudo chmod +x /usr/local/bin/getmetadata`
* Optional - install xmltodict which unlocks ALL meta data avilable (recommended to get the full use out of this tool)
    * enter the following command `sudo pip3 install xmltodict`
### Windows Installation (coming soon)

## Usage
* In your terminal, change to the directory that contains either MOV or MP4 files downloaded directly from a Lumix camera 
* Run the following command `getmetadata`
* If the command ran successfully, you will see a list of video files that were found with metadata
* In the directory where you ran the command, look for a file called **resolve-metadata.csv**
* In resolve, either create a new project or open a new project.
* Once inside the project go to the media pool (cut or edit tab)
* Go to the file menu
    * Select **Import Metadata To**
    * select **Media Pool**
* Select the **resolve-metadata.csv** file in the directory where you ran the command
* In the metadata import dialog
    * Note, if clips you'd like to add the metadata to are inside a bin, you must perform the inmport once inside the bin
    * Deselect the **Match using clip start and end time code**
    * In merge options, choose the **Update all metadata fields in the source file option**
    * You should see a confirmation that the metadata was imported
* Head to the edit tab and click the meta data tab and either select **All** or **Camera**
* Select a click from the media pool and you should now see the metadata

