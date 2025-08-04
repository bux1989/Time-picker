# Time Picker Component

A lightweight time picker component for WeWeb, refactored from a full date-time picker to focus exclusively on time selection with business hour restrictions.

## 🕒 Features

- **Time-only selection** - No date picker UI, only time selection
- **Business hours restriction** - Limited to 07:00 - 17:00 (7 AM to 5 PM)
- **Localization support** - English and German placeholder text
- **Multiple time formats** - 12h/24h formats with optional seconds
- **Value exposure** - Selected time properly exposed for parent components
- **Clean UI** - Minimal, focused interface

## ⚙️ Configuration

### Time Formats
- `HH:mm` - 14:30 (24-hour format)
- `h:mm A` - 2:30 PM (12-hour format)  
- `HH:mm:ss` - 14:30:00 (with seconds)
- `h:mm:ss A` - 2:30:00 PM (12-hour with seconds)

### Available Properties
- `enableSeconds` - Enable/disable seconds display
- `use24` - 24-hour vs 12-hour format (default: true)
- `autoApply` - Auto-apply time selection
- `lang` - Language for localization ('en', 'de')
- `format` - Time display format
- `stickedTimePicker` - Render at trigger level vs overlay

## 🚫 Time Restrictions

- **Minimum Time:** 07:00 (7:00 AM)
- **Maximum Time:** 17:00 (5:00 PM)
- **Purpose:** Business hours compliance
- **Implementation:** Built into component logic

## 🌐 Localization

- **English:** "Select time"
- **German:** "Zeit auswählen"

## 🔧 Technical Details

### Changed Files
- `src/wwElement.vue` - Main component refactored for time-only mode
- `ww-config.js` - Configuration simplified and updated

### Preserved Files  
- `src/vue-datepicker.js` - VuePic DatePicker library
- `src/main.css` - Component styling
- `package.json` - Dependencies

## 📦 Installation

This is a WeWeb component. Use as you would any WeWeb element in your project.

## 🎯 Usage Example

```vue
<time-picker
  :lang="'en'"
  :use24="true"
  :enableSeconds="false"
  :format="'HH:mm'"
  :autoApply="true"
  @change="handleTimeChange"
/>
```

The component will emit a `change` event with the selected time value when the user selects a time.
