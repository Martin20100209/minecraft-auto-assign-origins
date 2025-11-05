# Auto Assign Origins Mod

A Minecraft Fabric mod for version 1.21.1 that automatically assigns Origins to specific players based on their usernames and makes Wardens drop Totems of Undying with 100% chance.

## Features

- **Automatic Origin Assignment**: Players are automatically assigned Origins based on their usernames
- **No Origin Selection**: Players cannot choose their Origin - it's automatically determined by their username
- **Warden Loot Enhancement**: Wardens drop Totems of Undying with 100% chance
- **Origins Mod Compatible**: Fully compatible with the Origins mod for Fabric
- **Configurable**: Easy to modify username-to-Origin mappings

## User Assignments

The following players will be automatically assigned these Origins:

| Username | Assigned Origin |
|----------|----------------|
| Fishy01003 | Merling (Water-based) |
| 52bm | Elytrian (Flight/Nature) |
| Green_boii | Phantom (Swamp-like) |
| Balo01003 | Blazeborn (Stone/Fire) |
| Temsync | Enderian (Echo/Void) |
| Polocol | Blazeborn (Fire) |
| Snowfester | Feline (Frost-like) |
| Fkoe | Merling (Amphibian) |
| _Kitax | Phantom (Shadow) |

## Requirements

- Minecraft 1.21.1
- Fabric Loader 0.15.11+
- Fabric API
- Origins Mod 1.12.5+
- Apoli 2.9.0+

## Installation

### Option 1: Download Pre-built JAR (Recommended)

1. Go to the [Releases](https://github.com/Martin20100209/minecraft-auto-assign-origins/releases) page
2. Download the latest `auto-assign-origins-1.0.0.jar` file
3. Place the JAR file in your Minecraft `mods` folder
4. Install the required dependencies listed above
5. Launch Minecraft with Fabric

### Option 2: Build from Source

1. **Prerequisites**:
   - Java 21 (required for Minecraft 1.21.1)
   - Git

2. **Clone the repository**:
   ```bash
   git clone https://github.com/Martin20100209/minecraft-auto-assign-origins.git
   cd minecraft-auto-assign-origins
   ```

3. **Build the mod**:
   ```bash
   ./gradlew build
   ```
   
   On Windows:
   ```cmd
   gradlew.bat build
   ```

4. **Find the built JAR**:
   The compiled mod will be in `build/libs/auto-assign-origins-1.0.0.jar`

5. **Install**:
   Copy the JAR file to your Minecraft `mods` folder

## Development Setup

If you want to modify the mod:

1. **Clone and import**:
   ```bash
   git clone https://github.com/Martin20100209/minecraft-auto-assign-origins.git
   ```
   
2. **Open in your IDE**:
   - IntelliJ IDEA: Open the project directory
   - VSCode: Install the Java extensions and open the directory

3. **Generate IDE files** (if needed):
   ```bash
   ./gradlew genEclipseRuns  # For Eclipse
   ./gradlew genIntellijRuns # For IntelliJ
   ```

4. **Run in development**:
   ```bash
   ./gradlew runClient  # Launch Minecraft client
   ./gradlew runServer  # Launch Minecraft server
   ```

## Configuration

To modify which Origins are assigned to which players:

1. Open `AutoAssignOriginsMod.java`
2. Modify the `USER_ORIGIN_MAPPING` HashMap:
   ```java
   put("PlayerName", "origins:origin_id");
   ```
3. Available Origin IDs include:
   - `origins:human`
   - `origins:enderian`
   - `origins:arachnid`
   - `origins:avian`
   - `origins:blazeborn`
   - `origins:elytrian`
   - `origins:feline`
   - `origins:merling`
   - `origins:phantom`
   - `origins:shulk`

4. Rebuild the mod and replace the JAR file

## How It Works

1. **Player Join Detection**: The mod listens for player join events
2. **Username Lookup**: Checks if the joining player's username is in the predefined mapping
3. **Origin Assignment**: If found, automatically assigns the specified Origin
4. **Warden Loot Modification**: Modifies the Warden's loot table to always drop Totems

## Technical Details

- **Fabric Loader**: Uses Fabric's event system for player join detection
- **Loot Table Modification**: Uses Fabric API's loot table events to modify Warden drops
- **Origins Integration**: Compatible with Origins mod's component system
- **Thread Safety**: Proper scheduling ensures Origin assignment happens safely

## Troubleshooting

### Common Issues

1. **Origins not being assigned**:
   - Check that the Origins mod is installed and working
   - Verify the username is spelled correctly in the mapping
   - Check the console for error messages

2. **Mod won't load**:
   - Ensure you have the correct Minecraft version (1.21.1)
   - Verify all dependencies are installed
   - Check that you're using Java 21

3. **Warden totems not dropping**:
   - Ensure the mod is running on the server (not just client)
   - Check console logs for loot table modification messages

### Debug Information

The mod provides extensive logging. Check your latest.log file for messages starting with `[AutoAssignOrigins]`.

## Contributing

Contributions are welcome! Please:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This mod is released under the MIT License. See the LICENSE file for details.

## Support

If you encounter issues:

1. Check the troubleshooting section above
2. Search existing GitHub issues
3. Create a new issue with:
   - Minecraft version
   - Fabric Loader version
   - Origins mod version
   - Error logs
   - Steps to reproduce

## Changelog

### Version 1.0.0
- Initial release
- Automatic Origin assignment for predefined users
- Warden Totem of Undying drops
- Minecraft 1.21.1 compatibility
- Full Origins mod integration