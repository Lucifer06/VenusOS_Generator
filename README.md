With a simple setup where the Generator is not managed (manuel start) by Venus OS and when using a MultiPlus with only 1x AC input, I found annoying to see the main screen interface still displaying the AC source coming from the grid while in fact the AC source is coming from the Generator I started manually.

I thought that adding a Digital Multi Control GX panel would solve the problem, as it effectively knows the generator is running if we close the contact of it's connector on the back of the board, but long story short: it doesn't solve the display issue :-(



So here we are with my solution:

The solution is essentially using Node-RED to read a Digital input to know if the generator is running and then to write to the dbus interface the AC source.

To know that the generator is running, a simple contact that needs to be closed. I personally use and additional relai of the ATS (Automatic Transfer Switch) to feed the Digital Input of the Cerbo GX (actually the proposed flow here is using an external Digital Input from the RGPIO project (https://github.com/Lucifer06/Venus_rgpio).

The Node-RED flow is then calling the bash that issue the write dbus command.

Both VRM portal and Venus Display are now correctly displaying the AC source.

That simple.

The repository is here: VenusOS_Generator
