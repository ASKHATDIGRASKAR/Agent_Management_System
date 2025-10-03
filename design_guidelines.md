# Design Guidelines: Agent Management & List Distribution Platform

## Design Approach: Modern Dashboard System

**Selected Approach:** Dashboard-focused design system inspired by Linear, Notion, and modern SaaS tools  
**Justification:** Utility-focused application requiring clarity, efficiency, and data-dense layouts for admin workflows

**Core Principles:**
- Functional elegance over decorative elements
- Information hierarchy through typography and spacing
- Efficient workflows with minimal clicks
- Clear visual feedback for all actions

---

## Color Palette

**Light Mode:**
- Background: 0 0% 100% (pure white)
- Surface: 0 0% 98% (subtle gray for cards)
- Border: 220 13% 91% (soft dividers)
- Text Primary: 222 47% 11% (near black)
- Text Secondary: 215 14% 34% (muted gray)
- Primary Brand: 221 83% 53% (professional blue)
- Primary Hover: 221 83% 48%
- Success: 142 71% 45% (green for confirmations)
- Error: 0 84% 60% (red for validation errors)
- Warning: 38 92% 50% (amber for alerts)

**Dark Mode:**
- Background: 222 47% 11%
- Surface: 217 33% 17%
- Border: 217 19% 27%
- Text Primary: 210 40% 98%
- Text Secondary: 215 20% 65%
- Primary Brand: 217 91% 60%
- Primary Hover: 217 91% 65%

---

## Typography

**Font Families:**
- Primary: 'Inter' via Google Fonts (UI, data, forms)
- Monospace: 'JetBrains Mono' for data/numbers

**Hierarchy:**
- Page Titles: text-2xl md:text-3xl, font-semibold
- Section Headers: text-lg md:text-xl, font-semibold
- Card Titles: text-base, font-medium
- Body Text: text-sm, font-normal
- Helper Text: text-xs, text-muted
- Data/Numbers: text-sm, font-mono

---

## Layout System

**Spacing Primitives:** Use Tailwind units of 2, 4, 6, 8, 12, 16  
**Common patterns:** p-4, gap-6, space-y-8, mt-12

**Grid Structure:**
- Dashboard: Sidebar (w-64) + Main content (flex-1)
- Content max-width: max-w-7xl
- Form max-width: max-w-2xl
- Card padding: p-6
- Page padding: p-6 md:p-8

---

## Component Library

### Navigation & Layout

**Sidebar Navigation:**
- Fixed left sidebar (240px wide)
- Logo at top with 48px height
- Navigation items with icons (20px) + labels
- Active state: light background fill + accent border-left
- Hover state: subtle background lightening
- Bottom section: User profile with logout

**Top Bar:**
- Height: 64px
- Contains page title, breadcrumbs, and action buttons
- Right side: notifications bell, dark mode toggle, profile avatar

### Forms & Inputs

**Login Form:**
- Centered card (max-w-md)
- Logo above form
- Input fields with labels above
- Full-width primary button
- Error messages below inputs in error color
- "Remember me" checkbox

**Agent Creation Form:**
- Two-column layout on desktop (md:grid-cols-2)
- Single column on mobile
- Input groups: Name, Email, Mobile (with country code dropdown), Password
- Country code dropdown: Flag icon + code (e.g., +1)
- Form validation with inline error states
- Submit button: Primary, full-width on mobile

**CSV Upload:**
- Drag-and-drop zone with dashed border
- File icon (48px) centered
- "Drag & drop or click to browse" text
- Accepted formats shown: .csv, .xlsx, .xls
- File preview after upload with filename and size
- Validation errors displayed prominently

### Data Display

**Agent List/Table:**
- Clean table with subtle borders
- Headers: sticky positioning
- Columns: Name, Email, Mobile, Assigned Contacts, Actions
- Alternating row backgrounds for readability
- Hover state: subtle background change
- Action buttons: Edit (pencil icon), Delete (trash icon)
- Empty state: centered icon + message

**Distribution Visualization:**
- Card-based layout showing each agent
- Agent card includes: Avatar, Name, Contact count badge
- Visual indicator (progress bar or pie chart) for load balance
- List of contacts beneath each agent expandable/collapsible

**Contact Cards:**
- Compact card showing: FirstName, Phone, Notes
- Phone with clickable link (tel:)
- Notes truncated with "Read more" if long
- Subtle border-left accent per agent (color-coded)

### Feedback & Interactions

**Success States:**
- Toast notifications (top-right corner)
- Success icon + message
- Auto-dismiss after 3 seconds

**Loading States:**
- Skeleton loaders for tables
- Spinner for CSV processing
- Progress bar for file upload

**Empty States:**
- Centered icon (96px)
- Title + descriptive message
- CTA button to take action

---

## Animation Guidelines

**Minimal & Purposeful:**
- Sidebar navigation: No slide animations
- Hover states: 150ms transition on background/border
- Modal/Dialog: Simple fade-in (200ms)
- Toast notifications: Slide from right (250ms)
- Loading spinners: Smooth rotation
- Avoid: Page transitions, elaborate micro-interactions, scroll animations

---

## Accessibility

- Dark mode throughout with proper contrast ratios (WCAG AA)
- Form inputs: Clear labels, error states with icon + text
- Keyboard navigation: All interactive elements accessible via Tab
- Focus states: Visible outline on all focusable elements
- Screen reader: Semantic HTML, aria-labels for icon buttons

---

## Images

**No hero image required** - This is a utility dashboard application

**Icons:**
- Use Heroicons (outline style) via CDN
- Navigation: 20px icons
- Actions: 16px icons
- Empty states: 96px icons
- Consistency: All icons from same library

**Agent Avatars:**
- Circular, 40px diameter
- Initial-based placeholders (first letter of name)
- Background: gradient based on name hash

---

## Page-Specific Layouts

**Login Page:**
- Centered card on neutral background
- Minimal, focused design
- Logo + form + optional "Forgot password" link

**Dashboard Home:**
- Overview cards showing: Total Agents, Total Contacts, Recent Uploads
- Recent activity feed
- Quick actions: "Add Agent", "Upload CSV"

**Agent Management:**
- Top bar: "Add Agent" button (primary)
- Search/filter controls
- Agent table/grid below
- Pagination if >20 agents

**Upload & Distribution:**
- Two-step process: Upload → Review & Distribute
- Upload interface with drag-drop
- Distribution preview showing equal split
- Confirm button to execute distribution

**Agent Detail View:**
- Agent info header
- Tabs: Assigned Contacts, Activity Log
- Contact list with search/filter
- Export to CSV option