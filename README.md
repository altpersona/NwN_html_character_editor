# Neverwinter Nights Character Editor

A web-based character editor for Neverwinter Nights that allows you to load, edit, and save character data in JSON format. This tool provides a user-friendly interface for modifying all aspects of your NWN characters.

## Overview

This character editor is designed to work with JSON files exported from Neverwinter Nights `.bic` character files using the `nwn_gff` tool. It provides a comprehensive interface for editing all character attributes, stats, equipment, and more.

## Features

### Character Management
- **Load Character**: Import existing character JSON files
- **Save Character**: Export edited character data to JSON format
- **New Character**: Create new characters with default values

### Comprehensive Editing
- **Basic Information**: Name, age, gender, race, deity, alignment
- **Ability Scores**: Strength, Dexterity, Constitution, Intelligence, Wisdom, Charisma
- **Combat Stats**: Hit points, armor class, saving throws, attack bonus
- **Appearance**: Head type, colors, body parts, phenotype, portrait
- **Equipment**: Inventory management and equipped items
- **Feats**: Add, remove, and edit character feats
- **Skills**: Skill rank management
- **Class Information**: Class type, level, skill points

### User Interface
- **Tabbed Interface**: Organized sections for easy navigation
- **Dark Theme**: Neverwinter Nights-inspired styling
- **Responsive Design**: Works on desktop and mobile devices
- **Real-time Updates**: Changes are immediately reflected in the data

## Usage Instructions

### 1. Convert .bic to JSON
First, convert your Neverwinter Nights character file to JSON format:

```bash
nwn_gff -i red.bic -o red.json
```

### 2. Open the Character Editor
Open `character-editor.html` in your web browser.

### 3. Load Your Character
Click the "Load JSON File" button and select your character JSON file.

### 4. Edit Character Data
Navigate through the tabs and modify any fields:
- **Basic Info**: Character identity and basic statistics
- **Stats**: Ability scores and combat statistics
- **Appearance**: Visual customization options
- **Equipment**: Inventory and equipped items
- **Feats**: Character abilities and traits
- **Skills**: Skill ranks and proficiencies
- **Class**: Class information and progression

### 5. Save Your Changes
Click "Save JSON File" to export your edited character data.

### 6. Convert Back to .bic
Convert the JSON back to .bic format:

```bash
nwn_gff -i edited_character.json -o edited_character.bic
```

## Field Reference

### Basic Information
- **First Name/Last Name**: Character's name (supports localization)
- **Display Name**: Alternative display name
- **Description**: Character biography
- **Age**: Character age in years
- **Gender**: 0=Male, 1=Female
- **Race**: Race ID number
- **Deity**: Character's deity
- **Good/Evil**: Alignment scale (0-100)
- **Lawful/Chaotic**: Alignment scale (0-100)

### Ability Scores
- **Strength**: Physical power (1-50)
- **Dexterity**: Agility and reflexes (1-50)
- **Constitution**: Health and stamina (1-50)
- **Intelligence**: Mental acuity (1-50)
- **Wisdom**: Perception and insight (1-50)
- **Charisma**: Force of personality (1-50)

### Combat Statistics
- **Hit Points**: Current health
- **Max Hit Points**: Maximum health capacity
- **Armor Class**: Defense rating
- **Saving Throws**: Fortitude, Reflex, Will saves
- **Base Attack Bonus**: Combat proficiency

### Appearance
- **Appearance Type**: Character model type
- **Head Appearance**: Head model variation
- **Phenotype**: Body type (2=normal)
- **Portrait**: Character portrait reference
- **Colors**: Hair, skin, tattoo colors (0-255)
- **Body Parts**: Individual armor piece settings

### Equipment
- **Inventory Items**: Items carried by the character
- **Equipped Items**: Currently worn/wielded items

### Feats
Character abilities and special traits. Each feat is referenced by its ID number.

### Skills
Character skill proficiencies. Each skill has a rank value.

### Class Information
- **Class**: Character class ID
- **Class Level**: Current level in the class
- **Skill Points**: Available skill points
- **Epic Level**: Epic level progression

## Technical Details

### Data Format
The editor works with JSON files that follow the Neverwinter Nights GFF format structure. Each field includes:
- `type`: Data type (byte, short, int, dword, etc.)
- `value`: The actual value

### Browser Compatibility
- Modern browsers with JavaScript enabled
- Chrome, Firefox, Safari, Edge
- Mobile browsers supported

### File Size
Large character files with many items/feats may take longer to load/save.

## Troubleshooting

### File Won't Load
- Ensure the JSON file is properly formatted
- Check that the file was exported using `nwn_gff`
- Verify the file extension is `.json`

### Changes Not Saving
- Make sure to click "Save JSON File" after making changes
- Check browser download settings
- Verify file permissions

### Missing Fields
- Some fields may not be visible if they're not present in the original file
- The editor will create missing fields with default values when saving

### Performance Issues
- Large character files may take time to load
- Consider removing unnecessary items/feats to improve performance

## Advanced Usage

### Custom Default Values
Modify the `createNewCharacter()` function in the HTML file to set custom default values for new characters.

### Adding New Fields
The editor can be extended to support additional character attributes by:
1. Adding form fields to the appropriate tab
2. Updating the `updateUI()` and `updateDataFromUI()` functions
3. Adding default values to `createNewCharacter()`

### Batch Processing
For editing multiple characters, consider:
1. Creating a script to automate the conversion process
2. Using the editor's save/load functionality in a loop
3. Implementing custom batch processing logic

## Integration with nwn_gff

This editor is designed to work seamlessly with the `nwn_gff` tool:

### Conversion Workflow
1. Extract character from game files or modules
2. Convert `.bic` to `.json` using `nwn_gff`
3. Edit with this character editor
4. Convert back to `.bic` using `nwn_gff`
5. Import into game or module

### Compatibility
- Supports all standard Neverwinter Nights character fields
- Compatible with Enhanced Edition characters
- Works with custom content and mods

## Support

For issues or feature requests related to this character editor, please check:
- Browser console for error messages
- File format compatibility
- Network restrictions (for file loading)

## License

This character editor is provided as-is for educational and personal use with Neverwinter Nights.
