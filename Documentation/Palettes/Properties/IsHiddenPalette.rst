.. include:: /Includes.rst.txt

===============
isHiddenPalette
===============

.. confval:: isHiddenPalette

   :Path: $GLOBALS['TCA'][$table]['palettes']
   :type: boolean

   If set to true, this palette will never be shown, but the fields of the palette are technically
   rendered as hidden elements in FormEngine.

   This is sometimes useful when you want to set a field's value by JavaScript from another user-defined field.
   You can also use it along with the IRRE (TCA columns type :ref:`inline <columns-inline>`)
   :ref:`foreign_selector <columns-inline-properties-foreign-selector>` feature if you don't want the relation
   field to be displayed (it must be technically present and rendered though, that's why you should put it to
   a hidden palette in that case).

   .. note::
      The "isHiddenPalette" concept is more a hack than a solution in current FormEngine code. It has been
      introduced for the "FAL" file resource handling to have virtual fields which can be handled in JavaScript
      but are not displayed to the editor. It comes with the price of a bunch of HTML that is disabled
      via CSS if editing those records in the backend. The core will sooner or later reconsider this solution
      and substitute it with something more appropriate. Extension authors should stay away from this property
      if possible to not run into upgrade troubles if that happens.
