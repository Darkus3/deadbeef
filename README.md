# deadbeef: A smart IoT label ecosystem for retailer and supermaket

project goals:
- Ease consumer experience when shoping:
  - Enable user to "scan" (NFC, QRcode, ...?) the smart label for each item to buy, generate summary and total price of the shopping items at checkout
- Ease retailer experience of his product database management (pricing, quantity, inventory, ...).
  - Propose a back-end application for all his database management
  - Reflect the database information (prices, quantity,...) into smart labels wirelessly
  - Backend must generate a bill at checkout with shoped item of the customer (scanned items).


Architecture-definition:
Consumer will have a unique NFC tag (loyality card) that they can swipe to the label of there product they want to buy. Label will trigger the information to the Gateway and save this into the customer unique shopping list.
- Label (end-node) (1 product = 1 tag): 
  - MCU based (Cortex-M), low-power (battery based)
  - Display (eInk?): price, qr code, bar code
  - NFC reader

Retailer will put multiple gateways to cover the range of his shop. These devices will agreagate Up link data from end-node and interface with retailer cloud back-end.
- Gateway (N label for 1 GW - TBD): 
  - MPU based (Cortex-A)
  -  Protocol: Wifi for internet access, for communication with end-node TBD (LPWAN).
  -  Provisioning Labels
  -  Roll-out of new firmware update to end-node
  -  Down link update from retail app (price update, new qr code ...).
