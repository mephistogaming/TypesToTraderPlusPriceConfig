# TypesToTraderPlusPriceConfig
types to TP
===========

This folder is for making a TraderPlusPriceConfig.json snippet from a DayZ 
types XML file.

How to use it:

1. Put your types XML file in this same folder.
   Example: types.xml

2. Double-click run_types_to_tp.bat, or open this folder in PowerShell and run:
   python types_to_tp.py

3. The script will intelligently scan the type names and XML clues, then show
   a simple menu with three pricing choices.
   Examples include Weapons, Ammo, Weapon Attachments, Vests, Jackets and
   Shirts, Food, Drinks, Medical, Tools, Vehicles and Boats, Infected,
   Static World Objects, Vehicle Parts, and more.

   Pricing choices:

   1. Category pricing
      Set a fallback BuyPrice,SellPrice first if you want every item included.
      Press Enter on a category to use the fallback, enter a different price
      to override that category, or type skip to leave that category out.

   2. One default price for everything
      Enter one BuyPrice,SellPrice and every item gets that price.

   3. Price each item one by one
      Go through each item manually. You can set a fallback for every item,
      set a temporary category default, press Enter on an item to use the best
      available default, or type skip to leave an item out.

   Price format:

   BuyPrice,SellPrice

   Example:

   1000,500

4. The script creates:
   TraderPlusPriceConfig_snippet.json

5. Copy the entries inside "TraderCategories" into the TraderCategories list in
   your existing TraderPlusPriceConfig.json.

Product lines are created in this TraderPlus style:

ItemClassName,1,-1,-1,BuyPrice,SellPrice

The auto-categorizer uses class-name clues first. For example:

- Names containing Vest, PlateCarrier, or StabVest go into Vests.
- Names containing Jacket, Jacky, Shirt, Hoodie, Coat, or Parka go into
  Jackets and Shirts.
- Names that sound edible or drinkable go into Food or Drinks.
- Names that look like guns, ammo, optics, suppressors, or explosives are
  split into weapon-related categories.
- If the name is unclear, the script falls back to XML category/usage clues.

---

## License

This project is licensed under the **GNU General Public License v3.0**. 

See the [LICENSE](LICENSE) file for the full license text.
