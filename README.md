With a simple setup where the Generator is not managed by Venus OS, I found annoying to see the main screen interface still displaying the AC source coming from the grid while in fact the AC source is coming from the Generator I started manually.

The solution is essentially using Node-RED to read a Digital input to know if the generator is running and then to write to the dbus interface the AC source.

To know that the generator is running, a simple contact that needs to be closed. I personally use and additional relai of the ATS (Automatic Transfer Switch) to feed the Digital Input of the Cerbo GX (actually the proposed flow here is using an external Digital Input from the RGPIO project (https://github.com/Lucifer06/Venus_rgpio).

The Node-RED flow is then calling the bash that issue the write dbus command.

That simple.
