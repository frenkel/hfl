# Timer for Harvest
[Harvest](https://www.getharvest.com/) client implemented using
[GTK](https://www.gtk.org/) and [Rust](https://www.rust-lang.org/) for Linux
and the various BSD's.

## Screenshots

![Main window](/assets/main-window.png?raw=true "The main window")
![Popup](/assets/popup.png?raw=true "The time entry popup")

## Installation
On the Timer for Harvest github page, click on the releases link. The newest
release is listed at the top of the page. It contains pre-build binaries for
Ubuntu 19.10 and Fedora 31. Note that installing these **will not keep you
up-to-date** with the releases, because currently we don't provide package
repositories.

## Usage
After installation your GNOME installation should be able to find the
application when you type "Timer for Harvest" in the activity searcher.

### First usage
Upon first launch you will first see a web browser start. This will open an
authorization flow from Harvest. When you've completed these steps you will
end up on a white page with the text "Authorized successfully." The actual
application will start now.

### Daily usage
Just like the Harvest web interface there are some handy keyboard shortcuts:
- **F5** in the main window will refresh the time entries list. This can be
  usefull when you updated the entries using a different interface and
  Timer for Harvest still shows the old state.
- **N** in the main window opens the new time entry popup.
- **Esc** closes the time entry popup.
- **Enter** activates the "Save Timer" button in the time entry popup.

## Security
Username and password details are never seen by Timer for Harvest. A web
browser is used to authorize Timer for Harvest access to your account. This
authorization is stored in the form of an authorization token, which Harvest
lets expire in 14 days. Leaking this token would thus give somebody access to
your account for a maximum of 14 days.

The authorization token is currently stored on the file system, namely in
$XDG\_CONFIG\_HOME/timer-for-harvest.json. In the future we hope to move this
token to a more secure location, such as GNOME Seahorse.

## Wishlist
- Idle detection to ask user whether idle time should be subtracted or booked
  as a new time entry.
- Ability to see other days then today.
- Authentication token storage in GNOME Seahorse.
- Support for newlines in the notes entry field. This appears to only be
  possible with an GTK input field that supports markup, which looks strange.
