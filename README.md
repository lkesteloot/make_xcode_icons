# `make_xcode_icons`

This little utility creates all required icons for an Xcode project.

Xcode itself generates a `Contents.json` file that specifies all required
sizes. This program takes as input a large (e.g., 1024x1024) original file and
generates all required icons, updating the `Contents.json` file to point at
them.

# Requirements

The Python script requires PIL:

    % pip install Pillow

# Usage

Usage:

    % make_xcode_icons original.png icon_dir [default_size]

The optional `default_size` is used when the `Contents.json` file does not
specify a size. For one of my iOS projects this was 22, though for other
projects it wasn't necessary. Try the script without this parameter first;
it'll complain if it needs it.

For example:

    % make_xcode_icons original.png Images.xcassets/AppIcon.appiconset

Note that any existing (resized) icon files already in the icon directory
will be deleted. Keep your original elsewhere.

