


# 🎨 NanoUI

**A lightweight, zero-dependency Android UI library with 19 button styles and FAB with Speed Dial**

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Android](https://img.shields.io/badge/Android-5.0%2B-brightgreen)](https://developer.android.com)
[![Java](https://img.shields.io/badge/Java-17%2B-orange)](https://www.oracle.com/java/)
[![Size](https://img.shields.io/badge/Size-%3C100KB-success)](https://github.com/codebloomir-dev/NanoUI)

---

## 📦 Installation

### Method 1: Download AAR File

1. Download `nanoui-1.0.0.aar` from this repository
2. Create `app/libs/` folder in your project (if doesn't exist)
3. Place the AAR file in `app/libs/`
4. Add this line to your `build.gradle` (app module):

```gradle
dependencies {
    implementation files('libs/nanoui-1.0.0.aar')
}
```

5. Sync your project and you're ready to go! 🚀

---

Method 2: Using JitPack (Coming Soon)

```gradle
dependencies {
    implementation 'com.github.codebloomir-dev:NanoUI:1.0.0'
}
```

---

🚀 Quick Start

1. Normal Button

```xml
<com.codebloom.nanoui.NanoButton
    android:layout_width="match_parent"
    android:layout_height="56dp"
    android:text="Primary Button"
    app:nanoStyle="primary" />
```

2. Gradient Button

```xml
<com.codebloom.nanoui.NanoButton
    android:layout_width="match_parent"
    android:layout_height="56dp"
    android:text="🌊 Ocean"
    app:nanoStyle="gradient_ocean" />
```

3. FAB (Floating Action Button)

Step 1: Add to res/values/arrays.xml:

```xml
<array name="fab_menu_items">
    <item>@android:drawable/ic_menu_camera</item>
    <item>@android:drawable/ic_menu_gallery</item>
    <item>@android:drawable/ic_menu_send</item>
    <item>@android:drawable/ic_menu_add</item>
</array>
```

Step 2: Add FAB in XML:

```xml
<com.codebloom.nanoui.NanoFabButton
    android:id="@+id/fab"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:layout_gravity="bottom|end"
    android:layout_margin="24dp"
    app:fabSize="56dp"
    app:fabColor="teal"
    app:fabMenuCount="4"
    app:fabMenuItems="@array/fab_menu_items" />
```

Step 3: Handle clicks in Java:

```java
NanoFabButton fab = findViewById(R.id.fab);

fab.setOnMenuItemClickListener((position, iconRes) -> {
    switch (position) {
        case 0: // Camera
            // Open camera
            break;
        case 1: // Gallery
            // Open gallery
            break;
        case 2: // Send
            // Send message
            break;
        case 3: // Add
            // Add new item
            break;
    }
    fab.closeMenu();
});
```

---

🎨 Complete Button Styles (19 Styles)

Core Styles

# Style Name Description
1 primary Blue - Primary action
2 secondary Purple - Secondary action
3 success Green - Success/Confirm
4 danger Red - Danger/Delete
5 warning Yellow - Warning/Caution
6 info Teal - Information

Special Styles

# Style Name Description
7 rounded_neon Neon glowing circle
8 glass Glassmorphism effect
9 metallic Metallic/shiny finish
10 soft_shadow Soft shadow effect
11 minimal Minimal outline style
12 elevated Elevated with strong shadow

Gradient Styles

# Style Name Colors Description
13 gradient_sunset #F37335 → #FDC830 Warm sunset
14 gradient_ocean #2193B0 → #6DD5ED Cool ocean
15 gradient_fire #FF512F → #F09819 Fiery energy
16 gradient_forest #134E5E → #71B280 Nature & calm
17 gradient_midnight #232526 → #414345 Mysterious night
18 gradient_candy #FF6B6B → #FFD93D Sweet & playful
19 gradient_aurora #11998E → #38EF7D Magical aurora

---

🚀 FAB Features

FAB Colors

Color Enum Value Hex
Blue FabColor.BLUE #1A73E8
Purple FabColor.PURPLE #8E24AA
Green FabColor.GREEN #0F9D58
Red FabColor.RED #D93025
Orange FabColor.ORANGE #F57F17
Teal FabColor.TEAL #00BCD4

FAB Attributes

Attribute Description Default
fabSize FAB size in dp 72dp
fabElevation Shadow elevation 12dp
fabIconSize Icon size 32dp
fabMenuOffset Menu offset from FAB 16dp
fabMenuCount Number of menu items (1-6) 0
fabMenuItems Array of icon resources -
fabColor FAB color blue

---

🛠️ Customization

NanoButton Attributes

Attribute Format Description
nanoStyle enum Button style (see list above)
nanoCornerRadius dimension Corner radius
nanoElevation dimension Shadow elevation
nanoTextColor color Custom text color
nanoBackgroundColor color Custom background color
nanoRippleColor color Ripple effect color
nanoIcon reference Icon drawable
nanoIconGravity enum Icon position (start, end, top, bottom)
nanoIconPadding dimension Padding between icon and text
nanoIconSize dimension Icon size

Java Methods for NanoButton

```java
// Set style programmatically
btn.setNanoStyle(NanoButtonStyle.Style.GRADIENT_OCEAN);

// Customize appearance
btn.setNanoCornerRadiusDp(20);
btn.setNanoElevation(dpToPx(8));
btn.setNanoTextColor(Color.WHITE);
btn.setNanoRippleColor(Color.parseColor("#60FFFFFF"));

// Set icon
btn.setIcon(R.drawable.ic_star);
btn.setIconGravity(Gravity.START);
btn.setIconPadding(16);
btn.setIconSize(32);

// Set text
btn.setNanoText("Custom Button");
btn.setNanoTextSize(18);
btn.setNanoPadding(20, 14);
```

Java Methods for NanoFabButton

```java
// Set size
fab.setFabSize(72);

// Set color
fab.setFabColor(NanoFabButton.FabColor.PURPLE);
// or
fab.setFabColor("#8E24AA");

// Set menu items
int[] icons = {
    R.drawable.ic_camera,
    R.drawable.ic_gallery,
    R.drawable.ic_send
};
fab.setMenuItems(icons);

// Set position
fab.setFabGravity(Gravity.BOTTOM | Gravity.END);
fab.setFabMargin(24);

// Control menu
fab.openMenu();
fab.closeMenu();
fab.toggleMenu();
```

---

🔧 Requirements

· Minimum SDK: API 21 (Android 5.0)
· Target SDK: API 34 (Android 14)
· Language: Java 17
· Dependencies: None! ✅





---

🤝 Contributing

1. Fork the repository
2. Create your feature branch (git checkout -b feature/AmazingFeature)
3. Commit your changes (git commit -m 'Add some AmazingFeature')
4. Push to the branch (git push origin feature/AmazingFeature)
5. Open a Pull Request





---

💬 Contact

CodeBloom

· 🐙 GitHub: @codebloomir-dev
· 📧 Email: codebloomir@gmail.com

---

⭐ Show Your Support

If you like this project, please give it a ⭐ on GitHub!

https://img.shields.io/github/stars/codebloomir-dev/NanoUI

---

Made with ❤️ by CodeBloom

