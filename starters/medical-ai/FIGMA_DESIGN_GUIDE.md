# Medical AI Website - Figma Design Guide

## 🎨 设计概念总览

基于我们创建的医疗AI网站，这里是在Figma中重现设计的完整指南。

## 📐 设计规格

### 颜色系统
```
Primary Colors:
- Medical Blue: #1565C0
- Healthcare Cyan: #00ACC1
- Success Green: #48BB78
- Warning Orange: #FF7043

Neutral Colors:
- Background: #FFFFFF
- Secondary Background: #F7FAFC
- Text: #1A202C
- Light Text: #4A5568
- Border: #E2E8F0
```

### 字体系统
```
Primary Font: Inter or SF Pro Display
Secondary Font: Roboto or system font

Sizes:
- Hero Title: 48px (Desktop) / 32px (Mobile)
- Section Title: 36px (Desktop) / 24px (Mobile)
- Body Text: 16px
- Caption: 14px
```

### 间距系统
```
Spacing Scale: 8px base unit
- xs: 4px
- sm: 8px
- md: 16px
- lg: 24px
- xl: 32px
- 2xl: 48px
- 3xl: 64px
```

## 🏗️ 页面结构

### 1. Hero Section
```
Layout: Full-width container with centered content
Background: Gradient from Medical Blue to darker blue
Height: 100vh (full screen)

Elements:
- Main headline: "Revolutionizing Healthcare with AI"
- Subtitle: Healthcare description
- Primary CTA: "Explore AI Solutions" (button)
- Secondary CTA: "View Case Studies" (link)
- Announcement banner at top
```

### 2. Statistics Section
```
Layout: 4-column grid (2x2 on mobile)
Background: Light gray (#F7FAFC)

Stats:
- 95% Diagnostic Accuracy Rate
- 10M+ Medical Images Analyzed
- 500+ Healthcare Facilities Using Our AI
- 24/7 AI-powered Monitoring

Each stat:
- Large number (48px)
- Description below (16px)
```

### 3. Features Section
```
Layout: 3-column grid (1 column on mobile)
Background: White

Features (6 cards):
1. Medical Imaging AI - Icon: Camera
2. Predictive Analytics - Icon: Chart Bar
3. Natural Language Processing - Icon: Document Text
4. Real-time Monitoring - Icon: Heart
5. Drug Discovery - Icon: Beaker
6. Clinical Decision Support - Icon: Lightbulb

Each card:
- Icon (24px)
- Title (20px, bold)
- Description (16px)
```

### 4. CTA Section
```
Layout: Centered content card
Background: Medical Blue gradient
Text: White

Content:
- Title: "Ready to Transform Healthcare with AI?"
- Description paragraph
- CTA button: "Request Demo"
```

## 🎯 Figma设计步骤

### Step 1: 设置画板
1. 创建新的Figma文件：「Medical AI Website」
2. 创建画板：
   - Desktop: 1440px width
   - Tablet: 768px width  
   - Mobile: 375px width

### Step 2: 建立设计系统
1. **颜色样式**：
   - 创建所有主要颜色的颜色样式
   - 命名：Primary/Medical-Blue, Primary/Healthcare-Cyan 等

2. **文字样式**：
   - Hero/Title: 48px, Bold
   - Section/Title: 36px, Semibold
   - Body/Regular: 16px, Regular
   - Caption/Small: 14px, Regular

3. **组件库**：
   - Button/Primary: Medical Blue背景
   - Button/Secondary: 透明背景，蓝色边框
   - Card: 白色背景，阴影，圆角8px
   - Icon: 24px统一尺寸

### Step 3: 设计各个区块

#### Hero Section
```
Frame: 1440x800px
Background: Linear gradient (135°)
  - Start: #1565C0
  - End: #0D47A1

Content (居中):
- Announcement bar (top)
- Main title (48px, white, bold)
- Subtitle (18px, white, regular)
- Button group (Primary + Secondary)
```

#### Statistics Section
```
Frame: 1440x200px
Background: #F7FAFC
Padding: 64px

Grid: 4 columns, gap 32px
Each stat card:
- Number: 64px, Medical Blue, bold
- Label: 16px, gray, 2 lines
```

#### Features Section
```
Frame: 1440x600px
Background: White
Padding: 80px 0

Grid: 3x2, gap 32px
Each feature card:
- Icon: 32px, Medical Blue
- Title: 20px, bold, dark
- Description: 16px, gray
- Padding: 24px
```

### Step 4: 响应式设计
1. 复制Desktop版本到Tablet画板
2. 调整栅格：从3列改为2列
3. 复制到Mobile画板
4. 调整为单列布局
5. 缩小字体尺寸

### Step 5: 交互原型
1. 添加按钮hover状态
2. 创建页面间跳转
3. 添加滚动交互
4. 设置移动端手势

## 🔧 Figma资源和插件

### 推荐插件：
1. **Iconify** - 医疗相关图标
2. **Unsplash** - 医疗背景图片
3. **Content Reel** - 医疗文案内容
4. **Auto Layout** - 响应式布局
5. **Stark** - 可访问性检查

### 图标资源：
- Heroicons (心电图、心脏、大脑图标)
- Medical Icons (针管、药丸、听诊器)
- Feather Icons (通用UI图标)

### 图片资源：
- 医疗设备照片
- 医生和患者图片
- 科技感背景图
- 医疗数据可视化图表

## 📱 导出设置

### 为开发准备资源：
1. **图标**：SVG格式，24x24px
2. **图片**：
   - @1x: 原始尺寸
   - @2x: 2倍尺寸（Retina显示器）
   - WebP格式优化（较小文件大小）

3. **颜色代码**：导出CSS变量
4. **字体**：记录字体family和weight

## 🚀 从Figma到代码

使用我们配置的Figma MCP，您可以：

1. **提取设计数据**：自动获取颜色、字体、间距
2. **生成组件代码**：基于Figma组件生成React/Vue组件
3. **导出资源**：批量导出图标和图片
4. **同步更新**：设计变更时自动更新代码

## 🎨 设计检查清单

- [ ] 所有颜色使用设计系统中的颜色样式
- [ ] 文字大小符合类型比例
- [ ] 间距使用8px网格系统
- [ ] 组件可复用且一致
- [ ] 响应式布局在所有设备上正常
- [ ] 可访问性对比度符合WCAG标准
- [ ] 所有交互状态已定义
- [ ] 导出设置已配置

## 💡 下一步

1. 在Figma中创建这个设计
2. 使用Figma MCP工具提取设计数据
3. 将设计数据应用到Hugo网站
4. 建立设计-开发工作流程

现在您可以使用这个指南在Figma中重现医疗AI网站的设计！