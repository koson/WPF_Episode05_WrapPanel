# สคริปต์การสอน: WPF Episode 05 - WrapPanel

## เนื้อหาที่จะสอน

### 1. WrapPanel คืออะไร
- Panel ที่เรียง Element แล้วขึ้นบรรทัดใหม่อัตโนมัติ
- ต่างจาก StackPanel อย่างไร

### 2. Properties สำคัญ
- Orientation
- ItemWidth และ ItemHeight

### 3. ตัวอย่างการใช้งานจริง
- Color Palette
- Vertical Wrapping
- Tag Cloud

---

## ส่วนที่ 1: Introduction (0:00 - 2:00)

**สวัสดีครับทุกคน**

ยินดีต้อนรับกลับมาสู่ WPF Tutorial Series ของเรา

วันนี้เราจะมาเรียนรู้เกี่ยวกับ **WrapPanel** ซึ่งเป็น Layout Panel ที่น่าสนใจมากครับ

ในตอนที่แล้ว เราได้เรียนรู้เกี่ยวกับ StackPanel ไปแล้ว ซึ่ง StackPanel จะเรียง Element ไปเรื่อยๆ 
แต่มันจะไม่ขึ้นบรรทัดใหม่ ถ้าเต็มมันก็จะล้น (Overflow) ออกไป

**WrapPanel แก้ปัญหานี้ได้ครับ!** 

มันจะเรียง Element เหมือน StackPanel แต่เมื่อเต็มบรรทัด มันจะขึ้นบรรทัดใหม่อัตโนมัติเลย!

---

## ส่วนที่ 2: ทบทวน StackPanel (2:00 - 5:00)

### Demo 2.1: StackPanel ปกติ

เริ่มต้นด้วย StackPanel แบบ Horizontal ก่อนนะครับ

```xml
<StackPanel Orientation="Horizontal">
    <Button Content="1" Width="80" Height="80"/>
    <Button Content="2" Width="80" Height="80"/>
    <Button Content="3" Width="80" Height="80"/>
    <Button Content="4" Width="80" Height="80"/>
    <Button Content="5" Width="80" Height="80"/>
    <Button Content="6" Width="80" Height="80"/>
    <Button Content="7" Width="80" Height="80"/>
    <Button Content="8" Width="80" Height="80"/>
</StackPanel>
```

### Demo 2.2: ปัญหาของ StackPanel

**ลองรัน และ Resize Window ดู!**

**❌ พบปัญหา!** 

เมื่อ Window แคบ Button ก็จะล้นออกนอกหน้าจอ ไม่มีการขึ้นบรรทัดใหม่

เราต้อง Scroll แนวนอนเพื่อดู Button ที่เหลือ

**นี่คือข้อจำกัดของ StackPanel ครับ**

---

## ส่วนที่ 3: แนะนำ WrapPanel (5:00 - 10:00)

### Demo 3.1: เปลี่ยนเป็น WrapPanel

ตอนนี้เรามาลอง WrapPanel กันดูครับ

```xml
<WrapPanel>
    <Button Content="1" Width="80" Height="80"/>
    <Button Content="2" Width="80" Height="80"/>
    <Button Content="3" Width="80" Height="80"/>
    <Button Content="4" Width="80" Height="80"/>
    <Button Content="5" Width="80" Height="80"/>
    <Button Content="6" Width="80" Height="80"/>
    <Button Content="7" Width="80" Height="80"/>
    <Button Content="8" Width="80" Height="80"/>
</WrapPanel>
```

**ลอง Resize Window ดู!**

**✅ เห็นไหมครับ!**

Button จะขึ้นบรรทัดใหม่อัตโนมัติเมื่อพื้นที่ไม่พอ!

ไม่มี Scrollbar แนวนอนแล้ว Button จัดเรียงตัวเองให้สวยงามเสมอ

### Demo 3.2: ทำไมถึงเรียกว่า "Wrap"

คำว่า "Wrap" แปลว่า "พัน" หรือ "ห่อ"

เหมือนกับตอนเราพิมพ์ในโปรแกรม Word เมื่อพิมพ์ถึงสุดบรรทัด 
ข้อความจะ "ห่อ" ไปบรรทัดใหม่โดยอัตโนมัติ

WrapPanel ก็เหมือนกันครับ เมื่อ Element เต็มบรรทัด มันจะ "ห่อ" ไปบรรทัดใหม่!

---

## ส่วนที่ 4: Demo 1 - Color Palette (10:00 - 15:00)

### Demo 4.1: สร้าง Color Buttons

ตอนนี้เรามาสร้าง Color Palette กันครับ ใช้ปุ่มสีต่างๆ

```xml
<Border Background="White" 
        BorderBrush="LightGray" 
        BorderThickness="1" 
        Padding="10">
    <WrapPanel ItemWidth="80" ItemHeight="80">
        <Button Background="Red"/>
        <Button Background="Orange"/>
        <Button Background="Yellow"/>
        <Button Background="Green"/>
        <Button Background="Blue"/>
        <Button Background="Purple"/>
        <Button Background="Pink"/>
        <Button Background="Brown"/>
        <Button Background="Gray"/>
        <Button Background="Black"/>
        <Button Background="LightBlue"/>
        <Button Background="LightGreen"/>
        <Button Background="Coral"/>
        <Button Background="Gold"/>
        <Button Background="Violet"/>
    </WrapPanel>
</Border>
```

**อธิบาย:**
- `<Border>` - ใส่กรอบและพื้นหลังให้สวยงาม
- `ItemWidth="80"` - บังคับให้ทุก Item กว้าง 80 pixels
- `ItemHeight="80"` - บังคับให้ทุก Item สูง 80 pixels

### Demo 4.2: ลอง Resize Window

**ลอง Resize Window แล้วสังเกตดูครับ!**

- Window กว้าง → Button เรียงกันหลายตัว
- Window แคบ → Button จะขึ้นบรรทัดใหม่
- **Responsive โดยอัตโนมัติ!**

นี่คือจุดแข็งของ WrapPanel ครับ เหมาะกับ UI ที่ต้องการ Responsive

---

## ส่วนที่ 5: Properties ของ WrapPanel (15:00 - 22:00)

### 5.1 Orientation Property

เหมือน StackPanel มี 2 ค่า:

**Horizontal (Default)** - เรียงจากซ้ายไปขวา แล้วขึ้นบรรทัดใหม่

```xml
<WrapPanel Orientation="Horizontal">
    <Button Content="1" Width="80" Height="80"/>
    <Button Content="2" Width="80" Height="80"/>
    <Button Content="3" Width="80" Height="80"/>
</WrapPanel>
```

**Vertical** - เรียงจากบนลงล่าง แล้วขึ้น Column ใหม่

```xml
<WrapPanel Orientation="Vertical" Height="200">
    <Button Content="1" Width="60" Height="40"/>
    <Button Content="2" Width="60" Height="40"/>
    <Button Content="3" Width="60" Height="40"/>
    <Button Content="4" Width="60" Height="40"/>
    <Button Content="5" Width="60" Height="40"/>
    <Button Content="6" Width="60" Height="40"/>
</WrapPanel>
```

### 5.2 ItemWidth และ ItemHeight

**ItemWidth** - กำหนดความกว้างให้ทุก Item

**ItemHeight** - กำหนดความสูงให้ทุก Item

```xml
<WrapPanel ItemWidth="80" ItemHeight="80">
    <Button Background="Red"/>
    <Button Background="Green"/>
    <Button Background="Blue"/>
</WrapPanel>
```

**หมายเหตุ:** 
- ถ้าไม่กำหนด ItemWidth/ItemHeight แต่ละ Item จะใช้ขนาดของตัวเอง
- การกำหนด ItemWidth/ItemHeight ทำให้ Layout สม่ำเสมอและสวยงาม

### 5.3 Properties อื่นๆ

เหมือน Panel อื่นๆ

```xml
<WrapPanel Margin="20"
           Background="LightGray"
           HorizontalAlignment="Center"
           VerticalAlignment="Top">
    <!-- Items here -->
</WrapPanel>
```

**สรุป Properties สำคัญ:**
- **Orientation**: Horizontal (default) หรือ Vertical
- **ItemWidth**: ความกว้างของแต่ละ Item
- **ItemHeight**: ความสูงของแต่ละ Item
- **Margin, Background, Alignment**: เหมือน Panel อื่นๆ

---

## ส่วนที่ 6: Demo 2 - Vertical WrapPanel (22:00 - 26:00)

### Demo 6.1: Vertical Orientation

ลองเปลี่ยนเป็น Vertical ดูครับ

```xml
<Border Background="White" 
        BorderBrush="LightGray" 
        BorderThickness="1" 
        Padding="10" 
        Height="200">
    <WrapPanel Orientation="Vertical" ItemWidth="60" ItemHeight="40">
        <Button Content="1" Background="LightBlue"/>
        <Button Content="2" Background="LightGreen"/>
        <Button Content="3" Background="LightCoral"/>
        <Button Content="4" Background="LightGoldenrodYellow"/>
        <Button Content="5" Background="LightPink"/>
        <Button Content="6" Background="LightSalmon"/>
        <Button Content="7" Background="LightSeaGreen"/>
        <Button Content="8" Background="LightSkyBlue"/>
    </WrapPanel>
</Border>
```

**อธิบาย:**
- `Orientation="Vertical"` - เรียงจากบนลงล่าง
- `Height="200"` - จำกัดความสูง เพื่อให้เห็น Wrap
- เมื่อเต็มความสูง จะขึ้น Column ใหม่ทางขวา

### Demo 6.2: ความแตกต่าง Horizontal vs Vertical

**Horizontal WrapPanel:**
- เรียงจากซ้าย → ขวา
- เต็มบรรทัด → ขึ้นบรรทัดใหม่ด้านล่าง

**Vertical WrapPanel:**
- เรียงจากบน → ล่าง
- เต็มความสูง → ขึ้น Column ใหม่ทางขวา

---

## ส่วนที่ 7: Demo 3 - Tag Cloud (26:00 - 33:00)

### Demo 7.1: Tag Cloud คืออะไร

Tag Cloud เป็น UI Pattern ที่นิยมใช้ใน Blog, Website, StackOverflow

แสดง Tag หรือหัวข้อที่นิยม โดย:
- **ขนาดใหญ่** = นิยมมาก (มีบทความเยอะ)
- **ขนาดเล็ก** = นิยมน้อย (มีบทความน้อย)

WrapPanel เหมาะมากสำหรับทำ Tag Cloud!

### Demo 7.2: สร้าง Tag Cloud - Popular Tags (ใหญ่)

```xml
<WrapPanel>
    <!-- Programming Languages (Popular - Large) -->
    <Button Content="C#" 
            FontSize="24" 
            FontWeight="Bold" 
            Background="#9B59B6" 
            Foreground="White" 
            Padding="15,8" 
            Margin="5" 
            BorderThickness="0"/>
    
    <Button Content="Python" 
            FontSize="22" 
            FontWeight="Bold" 
            Background="#3498DB" 
            Foreground="White" 
            Padding="12,6" 
            Margin="5" 
            BorderThickness="0"/>
    
    <Button Content="JavaScript" 
            FontSize="20" 
            FontWeight="Bold" 
            Background="#F39C12" 
            Foreground="White" 
            Padding="10,5" 
            Margin="5" 
            BorderThickness="0"/>
</WrapPanel>
```

**อธิบาย:**
- `FontSize="24"` - ตัวใหญ่สุด = นิยมสูงสุด (150 บทความ)
- `FontSize="22"` - ตัวใหญ่ = นิยมมาก (120 บทความ)
- `FontSize="20"` - ตัวกลาง = นิยม (100 บทความ)
- สีต่างๆ ทำให้ดูน่าสนใจ

### Demo 7.3: เพิ่ม Medium Tags

```xml
<!-- Frameworks (Medium Popular) -->
<Button Content="WPF" 
        FontSize="18" 
        Background="#E74C3C" 
        Foreground="White" 
        Padding="8,4" 
        Margin="5" 
        BorderThickness="0"/>

<Button Content="React" 
        FontSize="18" 
        Background="#1ABC9C" 
        Foreground="White" 
        Padding="8,4" 
        Margin="5" 
        BorderThickness="0"/>

<Button Content=".NET" 
        FontSize="16" 
        Background="#16A085" 
        Foreground="White" 
        Padding="8,4" 
        Margin="5" 
        BorderThickness="0"/>
```

### Demo 7.4: เพิ่ม Small Tags

```xml
<!-- Topics (Less Popular - Small) -->
<Button Content="Desktop" 
        FontSize="14" 
        Background="#95A5A6" 
        Foreground="White" 
        Padding="6,3" 
        Margin="5" 
        BorderThickness="0"/>

<Button Content="Tutorial" 
        FontSize="14" 
        Background="#7F8C8D" 
        Foreground="White" 
        Padding="6,3" 
        Margin="5" 
        BorderThickness="0"/>

<Button Content="Database" 
        FontSize="12" 
        Background="#D5DBDB" 
        Foreground="#2C3E50" 
        Padding="5,2" 
        Margin="5" 
        BorderThickness="0"/>

<Button Content="Git" 
        FontSize="10" 
        Background="#FADBD8" 
        Foreground="#943126" 
        Padding="4,2" 
        Margin="5" 
        BorderThickness="0"/>
```

**สังเกตไหมครับ:**
- Tag ยิ่งนิยม → ขนาดใหญ่ → สีเข้ม
- Tag ยิ่งไม่นิยม → ขนาดเล็ก → สีอ่อน
- WrapPanel จัด Layout ให้อัตโนมัติ เรียงดูสวยงามเลย!

---

## ส่วนที่ 8: ตัวอย่างการใช้งานจริง (33:00 - 37:00)

### 8.1 Use Cases สำหรับ WrapPanel

**1. Tag Cloud** (เห็นใน Demo แล้ว)
- Blog tags
- Category labels
- Keyword display

**2. Image Gallery**
```xml
<WrapPanel ItemWidth="150" ItemHeight="150">
    <Image Source="photo1.jpg" Stretch="UniformToFill" Margin="5"/>
    <Image Source="photo2.jpg" Stretch="UniformToFill" Margin="5"/>
    <Image Source="photo3.jpg" Stretch="UniformToFill" Margin="5"/>
    <!-- More images -->
</WrapPanel>
```

**3. Toolbar with Auto-wrapping**
```xml
<WrapPanel Orientation="Horizontal">
    <Button Content="New" Width="80" Margin="2"/>
    <Button Content="Open" Width="80" Margin="2"/>
    <Button Content="Save" Width="80" Margin="2"/>
    <Button Content="Print" Width="80" Margin="2"/>
    <!-- ถ้า Window แคบ จะขึ้นบรรทัดใหม่อัตโนมัติ -->
</WrapPanel>
```

**4. Color Picker**
```xml
<WrapPanel ItemWidth="30" ItemHeight="30">
    <Rectangle Fill="Red" Margin="2"/>
    <Rectangle Fill="Orange" Margin="2"/>
    <Rectangle Fill="Yellow" Margin="2"/>
    <Rectangle Fill="Green" Margin="2"/>
    <!-- More colors -->
</WrapPanel>
```

**5. Badge Collection**
```xml
<WrapPanel>
    <Border Background="Blue" CornerRadius="10" Padding="10,5" Margin="3">
        <TextBlock Text="New" Foreground="White"/>
    </Border>
    <Border Background="Green" CornerRadius="10" Padding="10,5" Margin="3">
        <TextBlock Text="Popular" Foreground="White"/>
    </Border>
    <Border Background="Red" CornerRadius="10" Padding="10,5" Margin="3">
        <TextBlock Text="Hot" Foreground="White"/>
    </Border>
</WrapPanel>
```

---

## ส่วนที่ 9: WrapPanel vs StackPanel (37:00 - 40:00)

### เปรียบเทียบ StackPanel vs WrapPanel

| Feature | StackPanel | WrapPanel |
|---------|-----------|-----------|
| **การเรียง** | เส้นตรง ไม่ขึ้นบรรทัดใหม่ | ขึ้นบรรทัดใหม่อัตโนมัติ |
| **Overflow** | ล้นออกนอกหน้าจอ | Wrap ไปบรรทัดใหม่ |
| **Responsive** | ❌ ไม่ Responsive | ✅ Responsive |
| **Performance** | ✅ เร็วกว่า | ⚠️ ช้ากว่าเล็กน้อย |
| **Use Case** | Menu, Toolbar คงที่ | Tag Cloud, Gallery |

**เมื่อไหร่ควรใช้ WrapPanel:**
- ต้องการ Responsive Layout
- จำนวน Item ไม่แน่นอน
- Tag Cloud, Image Gallery
- Item มีขนาดไม่เท่ากัน

**เมื่อไหร่ควรใช้ StackPanel:**
- Layout เรียบง่าย ไม่ต้องการ Wrap
- จำนวน Item แน่นอน
- Menu, Toolbar ที่มีขนาดพอดี
- ต้องการ Performance

---

## ส่วนที่ 10: Tips & Best Practices (40:00 - 42:00)

### 10.1 ใช้ ItemWidth และ ItemHeight

```xml
<!-- ดี: Layout สม่ำเสมอ -->
<WrapPanel ItemWidth="100" ItemHeight="100">
    <Button Background="Red"/>
    <Button Background="Blue"/>
</WrapPanel>

<!-- ไม่ดี: ขนาดไม่เท่ากัน อาจดูไม่เรียบร้อย -->
<WrapPanel>
    <Button Width="80" Height="60" Background="Red"/>
    <Button Width="120" Height="90" Background="Blue"/>
</WrapPanel>
```

### 10.2 ใช้ Margin อย่างสม่ำเสมอ

```xml
<!-- ดี: Margin เท่ากันทุก Item -->
<WrapPanel>
    <Button Content="1" Margin="5"/>
    <Button Content="2" Margin="5"/>
    <Button Content="3" Margin="5"/>
</WrapPanel>

<!-- หรือใช้ Style -->
<WrapPanel>
    <WrapPanel.Resources>
        <Style TargetType="Button">
            <Setter Property="Margin" Value="5"/>
        </Style>
    </WrapPanel.Resources>
    <Button Content="1"/>
    <Button Content="2"/>
    <Button Content="3"/>
</WrapPanel>
```

### 10.3 Performance

- WrapPanel ช้ากว่า StackPanel เล็กน้อย (ต้องคำนวณ Wrap)
- ถ้ามี Item เยอะมาก (เกิน 1000) พิจารณาใช้ VirtualizingWrapPanel
- หรือใช้ ListBox/ItemsControl กับ WrapPanel เป็น ItemsPanel

### 10.4 Scrolling

```xml
<ScrollViewer VerticalScrollBarVisibility="Auto">
    <WrapPanel>
        <!-- Many items -->
    </WrapPanel>
</ScrollViewer>
```

---

## ส่วนที่ 11: Wrap Up และ Outro (42:00 - 45:00)

**สรุปสิ่งที่เราได้เรียนรู้วันนี้:**

1. ✅ WrapPanel คือ Panel ที่ขึ้นบรรทัดใหม่อัตโนมัติ
2. ✅ Properties สำคัญ:
   - Orientation (Horizontal/Vertical)
   - ItemWidth และ ItemHeight
3. ✅ สร้าง Color Palette
4. ✅ สร้าง Tag Cloud จริงๆ
5. ✅ เปรียบเทียบกับ StackPanel
6. ✅ Use Cases และ Best Practices

**WrapPanel เหมาะมากสำหรับ:**
- Tag Cloud และ Category Display
- Image Gallery ที่ต้องการ Responsive
- Toolbar ที่อาจ Overflow
- Badge และ Chip Collections

**ในตอนต่อไป:**

เราจะมาเรียนรู้เกี่ยวกับ **DockPanel** ซึ่งเป็น Panel ที่ใช้จัด Layout 
แบบ Dock ไปที่ขอบต่างๆ เช่น Top, Bottom, Left, Right 
เหมาะสำหรับทำ Main Window Layout!

**อย่าลืม:**
- กด Like ถ้าชอบ
- Subscribe เพื่อติดตามตอนต่อไป
- Comment บอกว่าอยากเรียนเรื่องอะไรต่อไป

**ขอบคุณที่รับชมครับ แล้วพบกันใหม่ตอนหน้า สวัสดีครับ!**

---

## เอกสารอ้างอิง

### Official Documentation
- [WrapPanel Class - Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/api/system.windows.controls.wrappanel)
- [Panels Overview - Microsoft Docs](https://docs.microsoft.com/en-us/dotnet/desktop/wpf/controls/panels-overview)

### Properties Reference
```
Orientation: Horizontal | Vertical
ItemWidth: Double
ItemHeight: Double
HorizontalAlignment: Left | Center | Right | Stretch
VerticalAlignment: Top | Center | Bottom | Stretch
Background: Color
Margin: Thickness
```

---

## Tips & Best Practices

1. **ItemWidth/ItemHeight**: ใช้เพื่อให้ Layout สม่ำเสมอและสวยงาม
2. **Responsive Design**: WrapPanel เหมาะสำหรับ UI ที่ต้อง Responsive
3. **Performance**: ถ้ามี Item มากๆ (>1000) พิจารณาใช้ Virtualization
4. **Scrolling**: ใช้ร่วมกับ ScrollViewer เมื่อมี Item เยอะ

---

## Code Examples

### Example 1: Simple Image Gallery
```xml
<ScrollViewer VerticalScrollBarVisibility="Auto">
    <WrapPanel ItemWidth="200" ItemHeight="200" Margin="10">
        <Border Margin="5" BorderBrush="Gray" BorderThickness="1">
            <Image Source="image1.jpg" Stretch="UniformToFill"/>
        </Border>
        <Border Margin="5" BorderBrush="Gray" BorderThickness="1">
            <Image Source="image2.jpg" Stretch="UniformToFill"/>
        </Border>
        <!-- More images -->
    </WrapPanel>
</ScrollViewer>
```

### Example 2: Color Picker
```xml
<WrapPanel ItemWidth="40" ItemHeight="40">
    <Rectangle Fill="Red" Margin="2" Cursor="Hand"/>
    <Rectangle Fill="Orange" Margin="2" Cursor="Hand"/>
    <Rectangle Fill="Yellow" Margin="2" Cursor="Hand"/>
    <Rectangle Fill="Green" Margin="2" Cursor="Hand"/>
    <Rectangle Fill="Blue" Margin="2" Cursor="Hand"/>
    <Rectangle Fill="Purple" Margin="2" Cursor="Hand"/>
</WrapPanel>
```

### Example 3: Badge List
```xml
<WrapPanel>
    <Border Background="#2196F3" CornerRadius="12" 
            Padding="12,6" Margin="4">
        <TextBlock Text="New Feature" Foreground="White" 
                   FontSize="12" FontWeight="Bold"/>
    </Border>
    <Border Background="#4CAF50" CornerRadius="12" 
            Padding="12,6" Margin="4">
        <TextBlock Text="Updated" Foreground="White" 
                   FontSize="12" FontWeight="Bold"/>
    </Border>
    <Border Background="#FF9800" CornerRadius="12" 
            Padding="12,6" Margin="4">
        <TextBlock Text="Beta" Foreground="White" 
                   FontSize="12" FontWeight="Bold"/>
    </Border>
</WrapPanel>
```

### Example 4: Responsive Toolbar
```xml
<WrapPanel Orientation="Horizontal">
    <Button Content="New" Width="80" Height="32" Margin="2">
        <Button.Style>
            <Style TargetType="Button">
                <Setter Property="Background" Value="#E0E0E0"/>
                <Style.Triggers>
                    <Trigger Property="IsMouseOver" Value="True">
                        <Setter Property="Background" Value="#BDBDBD"/>
                    </Trigger>
                </Style.Triggers>
            </Style>
        </Button.Style>
    </Button>
    <Button Content="Open" Width="80" Height="32" Margin="2"/>
    <Button Content="Save" Width="80" Height="32" Margin="2"/>
    <Button Content="Print" Width="80" Height="32" Margin="2"/>
    <Button Content="Export" Width="80" Height="32" Margin="2"/>
</WrapPanel>
```

---

## Common Mistakes (ข้อผิดพลาดที่พบบ่อย)

### ❌ ลืมกำหนด Width/Height
```xml
<!-- ผิด: Item ไม่มีขนาด จะไม่แสดงอะไร -->
<WrapPanel>
    <Button/>
    <Button/>
</WrapPanel>
```

### ✅ ถูกต้อง
```xml
<WrapPanel ItemWidth="80" ItemHeight="80">
    <Button Background="Red"/>
    <Button Background="Blue"/>
</WrapPanel>
```

### ❌ ใช้ WrapPanel กับ Item มากเกินไป
```xml
<!-- ผิด: Performance ต่ำ -->
<WrapPanel>
    <!-- 5000 items -->
</WrapPanel>
```

### ✅ ถูกต้อง
```xml
<!-- ใช้ VirtualizingWrapPanel หรือ ListBox แทน -->
<ListBox ScrollViewer.HorizontalScrollBarVisibility="Disabled">
    <ListBox.ItemsPanel>
        <ItemsPanelTemplate>
            <WrapPanel/>
        </ItemsPanelTemplate>
    </ListBox.ItemsPanel>
    <!-- Items with virtualization -->
</ListBox>
```

---

## แบบฝึกหัด

### Exercise 1: สร้าง Tag Cloud
สร้าง Tag Cloud สำหรับ Blog ของคุณ:
- อย่างน้อย 15 tags
- แบ่งเป็น 3 ระดับความนิยม (Large, Medium, Small)
- ใช้สีที่แตกต่างกัน

### Exercise 2: สร้าง Image Gallery
สร้าง Image Gallery:
- ใช้ WrapPanel แสดง thumbnail รูปภาพ
- รองรับ Resize Window
- เพิ่ม Border และ Shadow ให้สวยงาม

### Exercise 3: สร้าง Responsive Toolbar
สร้าง Toolbar ที่:
- มีปุ่มอย่างน้อย 10 ปุ่ม
- ขึ้นบรรทัดใหม่อัตโนมัติเมื่อ Window แคบ
- มี Icon และ Text ในแต่ละปุ่ม

---

## Code Examples Repository

Source code สำหรับ Episode นี้สามารถดาวน์โหลดได้ที่:
- GitHub: [WPF_Episode05_WrapPanel](https://github.com/koson/WPF_Episode05_WrapPanel)

---

**End of Script**