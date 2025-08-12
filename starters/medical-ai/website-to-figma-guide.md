# 从医疗AI网站到Figma设计的转换指南

## 🎯 目标
将现有的医疗AI网站转换为Figma设计文件，以便进行设计迭代和协作。

## 📊 网站结构分析

### 当前网站包含的页面：
1. **首页** (`_index.md`)
   - Hero区域：医疗AI革命主题
   - 统计数据：95%准确率、10M+图像、500+医疗机构、24/7监控
   - 功能特性：6大AI解决方案
   - CTA区域：立即体验

2. **文档页面** (`docs/`)
   - 入门指南
   - AI模型目录
   - 集成指南
   - API参考

3. **设计系统**
   - 主题：medical-ai.toml
   - 颜色：医疗蓝色主题
   - 组件：基于Hugo Blox模块

## 🎨 提取的设计信息

### 颜色系统（从 medical-ai.toml）
```css
/* Light Mode */
--primary: #1565C0;
--menu-primary: #1565C0;
--menu-text: #fff;
--menu-text-active: #00ACC1;
--accent-medical: #00ACC1;
--accent-success: #48BB78;
--accent-warning: #FF7043;

/* Dark Mode */
--primary-dark: #2196F3;
--accent-medical-dark: #00E5FF;
```

### 内容结构
```yaml
Hero Section:
  title: "Revolutionizing Healthcare with AI"
  subtitle: "Advanced artificial intelligence solutions..."
  primary_button: "Explore AI Solutions"
  secondary_button: "View Case Studies"
  announcement: "New: AI-powered diagnostic models with 95% accuracy"

Statistics:
  - "95% Diagnostic Accuracy Rate"
  - "10M+ Medical Images Analyzed" 
  - "500+ Healthcare Facilities Using Our AI"
  - "24/7 AI-powered Monitoring"

Features:
  - Medical Imaging AI (camera icon)
  - Predictive Analytics (chart-bar icon)
  - Natural Language Processing (document-text icon)
  - Real-time Monitoring (heart icon)
  - Drug Discovery (beaker icon)
  - Clinical Decision Support (lightbulb icon)
```

## 🛠️ 在Figma中重建的步骤

### Step 1: 创建Figma文件
1. 打开Figma，创建新文件：「Medical AI Website Design」
2. 设置画板：
   - Desktop: 1440px × 1024px
   - Mobile: 375px × 812px

### Step 2: 建立颜色样式
```
创建颜色样式：
- Primary/Medical-Blue: #1565C0
- Primary/Healthcare-Cyan: #00ACC1
- Success/Green: #48BB78
- Warning/Orange: #FF7043
- Neutral/White: #FFFFFF
- Neutral/Light-Gray: #F7FAFC
- Text/Dark: #1A202C
- Text/Light: #4A5568
```

### Step 3: 创建文字样式
```
字体：Inter (或 SF Pro Display)

样式：
- Hero/Title: 48px, Bold, Medical Blue
- Section/Title: 36px, Semibold, Dark
- Statistic/Number: 64px, Bold, Medical Blue
- Body/Regular: 16px, Regular, Dark
- Button/Text: 16px, Medium, White
```

### Step 4: 重建Hero区域
```
Frame: 1440 × 800px
Background: Linear gradient
  Start: #1565C0 (Medical Blue)
  End: #0D47A1 (Darker Blue)

Elements:
1. Announcement Bar (top)
   - Text: "New: AI-powered diagnostic models with 95% accuracy"
   - Background: rgba(255,255,255,0.1)
   - Border radius: 24px

2. Main Content (centered)
   - Title: "Revolutionizing Healthcare with AI"
   - Subtitle: "Advanced artificial intelligence solutions..."
   - Button Group:
     * Primary: "Explore AI Solutions" (White text, Medical Blue bg)
     * Secondary: "View Case Studies" (White text, transparent bg)
```

### Step 5: 重建统计区域
```
Frame: 1440 × 200px
Background: #F7FAFC
Padding: 64px horizontal

Layout: Auto layout, 4 items, space between
Each Statistic:
- Number: 64px, Bold, Medical Blue
- Description: 16px, Regular, Gray
- Spacing: 8px between number and text
```

### Step 6: 重建功能特性区域
```
Frame: 1440 × 600px
Background: White
Padding: 80px vertical, 120px horizontal

Layout: 3×2 Grid, 32px gap
Each Feature Card:
- Size: 360 × 200px
- Padding: 32px
- Background: White
- Border: 1px, #E2E8F0
- Border radius: 12px
- Shadow: 0 4px 12px rgba(0,0,0,0.05)

Card Content:
- Icon: 32px, Medical Blue
- Title: 20px, Semibold, Dark
- Description: 16px, Regular, Gray
- Vertical spacing: 16px
```

### Step 7: 创建组件
```
组件化元素：
1. Button/Primary
2. Button/Secondary  
3. Feature Card
4. Statistic Item
5. Navigation Header
6. CTA Section
```

### Step 8: 响应式设计
```
Mobile版本调整：
- Hero: 单列布局，小字号
- Statistics: 2×2网格
- Features: 单列卡片堆叠
- 间距缩小50%
```

## 🔄 从Figma回到代码的工作流

### 使用Figma MCP Pro:
1. **设计完成后**：在Figma中完成设计
2. **获取Figma文件ID**：从URL中复制文件ID
3. **使用MCP提取**：通过Figma MCP提取设计数据
4. **生成代码**：基于设计数据更新Hugo网站
5. **同步更新**：设计变更时重复流程

### 示例命令（未来使用）:
```bash
# 从Figma提取设计数据
# figma-mcp-pro extract --file-id YOUR_FIGMA_FILE_ID

# 生成React组件
# figma-mcp-pro generate --framework react --output ./components
```

## 📋 检查清单

创建Figma设计时确保：
- [ ] 所有颜色使用命名的颜色样式
- [ ] 文字使用一致的文字样式  
- [ ] 组件可复用且参数化
- [ ] 图层命名清晰有序
- [ ] 响应式变体已创建
- [ ] 交互状态已定义（hover, active等）
- [ ] 导出设置已配置
- [ ] 设计规范文档已创建

## 🚀 下一步行动

1. **立即开始**：使用这个指南在Figma中重建医疗AI网站
2. **工具准备**：确保已安装Iconify、Unsplash等插件
3. **团队协作**：邀请团队成员到Figma文件
4. **迭代设计**：基于用户反馈改进设计
5. **同步开发**：使用Figma MCP保持设计-代码同步

完成设计后，您将拥有：
- 专业的医疗AI网站设计文件
- 完整的设计系统和组件库
- 可复用的设计模板
- 设计-开发协作工作流