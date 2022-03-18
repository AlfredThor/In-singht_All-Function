# In-singht_All-Function
In-sight全部函数汇总
---
The Functions of In-Sight Explorer V3.3.0

### 视觉工具(提取并处理图像特征的函数)。

- I D(读取并检验线性条码和 2D 符号的函数)。

```shell script
ReadIDCode(Image, Fixture, Region, ...)
````

- 读取并可选择检验一维和二维条码及符号体系中包含的字母数字串。返回一个带有解码字符串的 IDCode 结构。

```shell script
 ValidateIDData(IDCode, 验证选项, ...)
````

- 对使用 ID 码解码的数据执行验证,返回 IDValid 结构。

```shell script
 VerifyIDCode(IDCode, ...)
````

对 IDMax? 解码的“数据矩阵”符号执行附加符号验证操作。返回 IDVerify 结构。

### 2.O CV/OCR(训练、检验和读取字符的函数)。

```shell script
 ReadText(Image, Fixture, Region, Font, ...)
````

- 查找并读取文本字符串中的字符。 返回文本结构。

```shell script
TrainFont(Image, Show)
````

- 使用 OCV/OCR 字集训练向导训练字集。 返回字集结构。

```shell script
VerifyText(Image, Fixture, Region, Font, String, Accept, Tune, Show)
````

### 查找并检验文本字符串中的字符。返回文本结构。

- 斑点（查找、分析斑点并对其进行分类的函数）。

```shell script
ExtractBlobs(Image, Fixture, Region, ...)
````

- 提取图像的斑点并可选择按区域对其进行排序。 返回斑点结构。

```shell script
FindBlobs(Blobs, Number to Find, ...)
````

- 用一组加权的标准值对斑点结构内的斑点评分。 返回斑点结构。

```shell script
SortBlobs(Blobs, Number to Sort, ...)
```

###按指定标准排序斑点结构。返回斑点结构。

- 边（定位直边或曲边的函数）。

```shell script
FindCircle(Image, Fixture, Annulus, ...)
```

- 找到最佳圆周边。返回边结构。

```shell script
FindCircleMinMax(Image, Fixture, Annulus, ...)
```

- 检查连续边的圆形。 返回边结构。

```shell script
FindCurve(Image, Fixture, Region, ...)
```

- 找到最佳曲边。 返回边结构。

```shell script
FindLine(Image, Fixture, Region, ...)
```
- 找到最佳直边。 返回边结构。

```shell script
FindMultiLine(Image, Fixture, Region, ...)
```

- 找到多条直边。返回边结构。

```shell script
FindSegment(Image, Fixture, Region, ...)
```

- 找到由黑色或白色片段定义的边对。 返回边结构。

```shell script
PairDistance(Edges, First Edge, Second Edge)
```

- 返回边对内各边之间的距离。

```shell script
PairEdges(Edges, Number of Pairs, ...)
```

```shell script
PairMaxDistance(Edges)
```

- 返回多个边对的最大边对距离。

```shell script
PairMeanDistance(Edges)
```

- 返回多个边对的平均边对距离。

```shell script
PairMinDistance(Edges)
```

- 返回多个边对的最小边对距离。

```shell script
PairSDevDistance(Edges)
```

- 返回多个边对的边对距离标准偏差。

```shell script
PairsToEdges(Edges, Number of Pairs, Show)
```

- 通过对线段取平均数将边对组合为单一边。 返回边结构。

```shell script
SortEdges(Edges, Number to Sort, Sort By, Show)
```

### 按照指定标准对边结构进行排序。 返回经排序的边结构。

- 图案匹配（训练、查找和排序图案的函数，包括 PatMax(R) 图案（如果可用）。

```shell script
FindPatMaxPatterns(Image, Fixture, Region, ...)
```

- 搜索图像内的图案。 返回图案结构。

```shell script
FindPatterns(Image, Fixture, Region, ...)
```

- 从图像提取区域或边模型；可选择搜索此类模型。 返回图案结构。

```shell script
SortPatterns(Patterns, Number to Sort, Sort By, Fixture, Show)
```

- 按照指定标准对图案结构排序。 返回经排序的图案结构。

```shell script
TrainPatMaxPattern(Image, Fixture, Region, ...)
```

- 提取并训练图像的图案以便和 FindPatMaxPatterns 一起使用。返回图案结构。

- 图象（处理图像的函数）。

```shell script
CompareImage(Image, Fixture, Region, ...)
```

- 比较关注区和模板图像。返回带有白色像素的图像结构，此区域与模板在特定容限内不匹配时返回白色像素。

```shell script
FindCircleDefects(Image, Fixture, Annulus, ...)
```

- 查找环形区域内的非圆形或非径向缺陷。 返回存储二进制阈值化图像的图像结构。

```shell script
NeighborFilter(Image, Fixture, Region, Operation, ...)
```

- 用根据各相邻像素的值更改每个像素的过滤器处理某一区域。返回存储所处理图像的图像结构。

```shell script
PointFilter(Image, Fixture, Region, Operation, ...)
```

- 用独立更改每个像素的过滤器处理某一区域，忽略相邻像素。 返回存储所处理图像的图像结构。

```shell script
ScaleImage(图像, 固定, 区域, 缩放类型, ...)
```

- 将图像区域重新调整为一个以左上角为原点的未旋转和未弯曲的矩形。返回存储所处理图像的图像结构。

- 直方图（提取并处理直方图的函数）。

```shell script
ExtractHistogram(Image, Fixture, Region, Show)
```

- 计算某个区域的灰度直方图。 返回 Hist 结构。

```shell script
HistContrast(Hist, [FirstBin, LastBin], [Color])
```

- 返回直方图的灰度对比度值。注意：如果引用 ColorHist 结构，则会添加 Color 参数。

```shell script
HistCount(Hist, [FirstBin, LastBin], [Color])
```

- 返回直方图的一定容器范围内的像素数。注意：如果引用 ColorHist 结构，则会添加 Color 参数。

```shell script
HistHead(Hist, [FirstBin, LastBin], [Color])
```

- 返回直方图的第一个非零灰度值的索引。注意：如果引用 ColorHist 结构，则会添加 Color 参数。

```shell script
PairMaxDistance(Edges)
```

- 返回多个边对的最大边对距离。

```shell script
PairMeanDistance(Edges)
```

- 返回多个边对的平均边对距离。

```shell script
PairMinDistance(Edges)
```

- 返回多个边对的最小边对距离。

```shell script
PairSDevDistance(Edges)
```

- 返回多个边对的边对距离标准偏差。

```shell script
PairsToEdges(Edges, Number of Pairs, Show)
```

- 通过对线段取平均数将边对组合为单一边。 返回边结构。

```shell script
SortEdges(Edges, Number to Sort, Sort By, Show)
```

### 按照指定标准对边结构进行排序。 返回经排序的边结构。

- 图案匹配（训练、查找和排序图案的函数，包括 PatMax(R) 图案（如果可用）。

```shell script
FindPatMaxPatterns(Image, Fixture, Region, ...)
```

- 搜索图像内的图案。 返回图案结构。

```shell script
FindPatterns(Image, Fixture, Region, ...)
```

- 从图像提取区域或边模型；可选择搜索此类模型。 返回图案结构。

```shell script
SortPatterns(Patterns, Number to Sort, Sort By, Fixture, Show)
```

- 按照指定标准对图案结构排序。 返回经排序的图案结构。

```shell script
TrainPatMaxPattern(Image, Fixture, Region, ...)
```

### 提取并训练图像的图案以便和 FindPatMaxPatterns 一起使用。返回图案结构。

- 图象（处理图像的函数）。

```shell script
CompareImage(Image, Fixture, Region, ...)
```

- 比较关注区和模板图像。返回带有白色像素的图像结构，此区域与模板在特定容限内不匹配时返回白色像素。

```shell script
FindCircleDefects(Image, Fixture, Annulus, ...)
```

- 查找环形区域内的非圆形或非径向缺陷。 返回存储二进制阈值化图像的图像结构。

```shell script
NeighborFilter(Image, Fixture, Region, Operation, ...)
```

- 用根据各相邻像素的值更改每个像素的过滤器处理某一区域。返回存储所处理图像的图像结构。

```shell script
PointFilter(Image, Fixture, Region, Operation, ...)
```

- 用独立更改每个像素的过滤器处理某一区域，忽略相邻像素。 返回存储所处理图像的图像结构。

```shell script
ScaleImage(图像, 固定, 区域, 缩放类型, ...)
```

### 将图像区域重新调整为一个以左上角为原点的未旋转和未弯曲的矩形。返回存储所处理图像的图像结构。

- 直方图（提取并处理直方图的函数）。

```shell script
ExtractHistogram(Image, Fixture, Region, Show)
```

- 计算某个区域的灰度直方图。 返回 Hist 结构。

```shell script
HistContrast(Hist, [FirstBin, LastBin], [Color])
```

- 返回直方图的灰度对比度值。注意：如果引用 ColorHist 结构，则会添加 Color 参数。

```shell script
HistCount(Hist, [FirstBin, LastBin], [Color])
```

- 返回直方图的一定容器范围内的像素数。注意：如果引用 ColorHist 结构，则会添加 Color 参数。

```shell script
HistHead(Hist, [FirstBin, LastBin], [Color])
```

- 返回直方图的第一个非零灰度值的索引。注意：如果引用 ColorHist 结构，则会添加 Color 参数。
返回表示直方图百分比的灰度级值索引。

```shell script
HistMax(Hist, [FirstBin, LastBin], [Color])
```

### 返回直方图的一定容器范围内的最普通（典型）的灰度值。

- 注意：如果引用 ColorHist 结构，则会添加 Color 参数。

```shell script
HistMean(Hist, [FirstBin, LastBin], [Color]
```

- 返回直方图的一定容器范围内的平均灰度值。

- 注意：如果引用 ColorHist 结构，则会添加 Color 参数。

```shell script
HistMin(Hist, [FirstBin, LastBin], [Color])
```

- 返回直方图的一定容器范围内的最不典型的灰度值。

- 注意：如果引用 ColorHist 结构，则会添加 Color 参数。

```shell script
HistSDev(Hist, [FirstBin, LastBin], [Color])
```

- 返回直方图的一定容器范围内的标准偏差值。

- 注意：如果引用 ColorHist 结构，则会添加 Color 参数。

```shell script
HistSum(Hist, [FirstBin, LastBin], [Color])
```

- 返回直方图的一定容器范围内的灰度值总和。

- 注意：如果引用 ColorHist 结构，则会添加 Color 参数。

```shell script
HistSumSquare(Hist, [FirstBin, LastBin], [Color])
```

- 返回直方图的一定容器范围内的值平方和。

- 注意：如果引用 ColorHist 结构，则会添加 Color 参数。

```shell script
HistTail(Hist, [FirstBin, LastBin], [Color])
```

- 返回直方图的一定容器范围的最后一个非零灰度值索引。

- 注意：如果引用 ColorHist 结构，则会添加 Color 参数。

```shell script
HistTailPercentage(Hist, Percentage, [FirstBin, LastBin], [Color])
```

- 返回表示直方图百分比的灰度级值索引。

```shell script
HistThresh(Hist, [FirstBin, LastBin], [Color])
```

- 返回直方图的最佳二进制阈值。

- 注意：如果引用 ColorHist 结构，则会添加 Color 参数。

### 几何（测量距离和角度或拟合几何形状的函数）。

- 测量（计算距离和角度的函数）。

```shell script
CircleToCircle(Circle 0, Circle 1, Show)
```

- 测量两个圆之间的最短距离。返回 Dist 结构。注意：如果两个圆彼此分离，距离为正值；相交时距离为 0.0；若包含，则为负值。

```shell script
LineToCircle(Line, Circle, Show)
```

- 测量直线到圆的最短距离。返回 Dist 结构。

- 注意：如果它们相交，则距离为 0.0，并且点就是交点。

```shell script
LineToLine(Line 0, Line 1, Show)
```

- 测量两条直线之间夹角（逆时针度数）。 返回 Dist 结构。注意：如果它们相交，则距离为 0.0。如果平行，则距离为正值且角度为 0、+180 或 ?180。

```shell script
MidLineToMidLine(Line 0, Line 1, Show)
```

- 测量两条线段中点之间的最短距离。返回 Dist 结构。

```shell script
PointToCircle(Point, Circle, Show)
```

- 测量点到圆的最短距离。 返回 Dist 结构。注意：如果点落在圆外，则距离为正；如果落在圆上，则距离为 0.0；如果在圆内，则距离为负。

```shell script
PointToPoint(Point 0, Point 1, Show)
```

- 测量两点之间的最短距离。返回 Dist 结构。

- 注意：如果 Point 0 = Point 1，则角度为 0.0。

```shell script
PointToPointAngle(Point 0, Point 1)
```

- 返回线段与图像行轴之间的角度。

- 注意：如果 Point 0 = Point 1，则角度为 0.0。

```shell script
PointToPointDistance(Point 0, Point 1)
```

- 返回两个点之间的距离。

- 拟合（构造几何形状的函数）。

```shell script
BoundingRectangle
```

- 基于所选的对齐方式，创建围绕斑点的界限矩形。

```shell script
CircleFromNPoints(Point Row 0, Point Col 0, Point Row 1, Point Col 1, Point Row 2, Point Col 2, [Point Row 3, Point Col 3, ..., Show])
```

- 通过系列点构造一个圆。返回 CircleFit 结构。

```shell script
LineFromNPoints(Point Row 0, Point Col 0, Point Row 1, Point Col 1, [Point Row 2, Point Col 2, ..., Show])
```

- 通过系列点构造一条直线。 返回 LineFit 结构。

```shell script
SegmentFromLines(Line 0, Line 1, Show)
```

- 通过对两条线段取平均数构造一条线段。 返回直线结构。

- 图形（在电子表格内放置和显示控件或显示图像内的图形的函数）。

- 控件（在电子表格上放置控件的函数。锁定电子表格时仍可对控件进行调整）。

```shell script
Button(Name, Trigger)
```

- 在单元格中插入带标签的按钮控件。单击它会返回 1.0；否则返回 0.0。

```shell script
CheckBox(Name)
```

- 在单元格中插入带标签的复选框控件。选中时返回 1.0；否则返回 0.0。

```shell script
Dialog(Label, Title, High, Wide)
```

- 创建通过带标签的按钮进行访问的对话。

```shell script
EditAnnulus(Fixture, Move, Size, Name, Show)
```

- 在单元格中插入交互式圆环控件。

```shell script
EditCircle(Fixture, Move, Size, Name, Show)
```

- 在单元格中插入交互式圆控件。

```shell script
EditFloat(Min, Max)
```

- 在单元格中插入数字编辑框控件。返回一个约束在 Min 到 Max 范围中的浮点值。

```shell script
EditInt(Min, Max)
```

- 在单元格中插入数字编辑框控件。返回一个约束在 Min 到 Max 范围中的整数。

```shell script
EditLine(Fixture, Move Point 0, Move Point 1, Name, Show)
```

- 在单元格中插入交互式直线控件。

```shell script
EditPoint(Fixture, Move, Name, Show)
```

- 在单元格中插入交互式点控件。

```shell script
EditRegion(Fixture, Move, Size, Rotate, Bend, Name, Show)
```

```shell script
EditString(Max String Length)
```

- 在单元格中插入字符串编辑框控件。返回约束在 0 到最大字符长度范围中的字符串。

```shell script
Link(标签, 主机名, 对话标签/左上方单元格, 光标位置)
```

- 创建到本地机或远程传感器上的对话或单元格的链接。标签/位置可以是主电子表格中的对话、向导或单元格位置的标签。

```shell script
ListBox(String0, [String1, ...])
```

- 在单元格中插入列表框。返回选定列表项从零开始的索引。

```shell script
MessageBox(Title, Text, Status, Timeout, Style)
```

- 弹出显示输入文本的消息框。

```shell script
Select(Title, Index, Auto, Control0, [Control1, ...])
```

- 使用变量列表中的 Index 参数打开对话、向导、链接或选择控件的函数。

```shell script
Wizard(Name, Mode, Dialog0, Dialog1, [Dialog2, ...])
```

- 通过对话框集合创建向导。将 Mode 设为 0 可在“菜单”模式下运行，或设置为 1 可在“序列”模式下运行。

- 图像（在图像上画图的函数）。

```shell script
PlotArc(Arc, Name, Color, Show)
```

- 绘制弧。

```shell script
PlotCircle(Circle, Name, Color, Show)
```

- 绘制圆。返回绘图结构。

```shell script
PlotCross(Cross, Name, Color, Show)
```

- 绘制交叉标记。返回绘图结构。

```shell script
PlotLine(Line, Name, Color, Show)
```

- 绘制直线。

```shell script
PlotPoint(Point, Name, Color, Show)
```

- 绘制点符号。 返回绘图结构。

```shell script
PlotRegion(Region, Name, Color, Show)
```

- 绘制区域。

```shell script
PlotString(String, Point, Color, Show)
```

- 绘制字符串。返回绘图结构。

- 显示（在电子表格上放置图形显示的函数）。

```shell script
Chart(Event, Value, Number, Name, Range:Min, Range:Max)
```

- 在单元格中插入发生每个事件时更新的图表显示。

```shell script
ColorLabel(Name, Fore Color, Back Color)
```

- 将指定颜色的字符串插入指定颜色的单元格中。

```shell script
MultiStatus(Value, Start Bit, Number of Bits, Reverse Order, Color 0, Color 1) 显示指示位值的一行 16 个状态灯。如果相应位等于 1，则显示 Color 1 的灯；否则显示 Color 0 的灯。
```

```shell script
Status(Status, Label:Green, Label:Yellow, Label:Red)
```

- 插入带有用户指定标签的模拟 LED 状态灯。

```shell script
StatusLight(Status, Label:Positive, Label:Zero, Label:Negative, ...)
```

- 插入带有标签的模拟 LED 状态灯；状态灯和标签的颜色均可由用户指定。

### 数学（数学函数和运算符）。

- 查找（查找函数）。

```shell script
Column(Cell)
```

- 返回电子表格单元格的列号。

- 注意：列 A = 0.0，列 Z = 25.0。

```shell script
CountError(Cell1, [Cell2, ...])
```

- 返回一个或多个单元格或单元格范围中的错误数。

```shell script
ErrFree(cell or cell-range)
```

- 将 #ERR 单元格转换为空单元格，以消除错误传播。

```shell script
If(Cond, Val1, Val2)
```

- 如果 Cond 为 TRUE，则返回 Val1；否则返回 Val2。

```shell script
MaxI(Val0, [Val1, ...])
```

- 返回可变长度值列表的最大值的索引。

```shell script
MinI(Val0, [Val1, ...])
```

- 返回可变长度值列表的最大值的索引。

```shell script
NthMaxI(N, Val0, [Val1, ...])
```

- 返回可变长度列表中的第 N 大的值的索引。

```shell script
NthMinI(N, Val0, [Val1, ...])
```

- 返回可变长度列表中的第 N 小的值的索引。

```shell script
Row(Cell)
```

- 返回电子表格单元格的行号。

```shell script
Switch(FindCase, Default, [Case0, Val0, Case1, Val1, ...]) 返回索引匹配项的值，否则返回默认值。
```

```shell script
逻辑（逻辑函数。TRUE = 非 0.0；FALSE = 0.0）。
```

```shell script
And(Val1, Val2, [Val3, ...])
```

- 返回可变长度值列表的逻辑与运算结果。

```shell script
BitAnd(Val1, Val2, [Val3, ...])
```

- 返回可变长度值列表的按位与运算结果。

- 注意：只处理较低的 16 位。

```shell script
BitNot(Val)
```

- 返回 Val 的逻辑取反运算结果。

- 注意：只处理较低的 16 位。

```shell script
BitOr(Val1, Val2, [Val3, ...])
```

- 返回可变长度值列表的按位或运算结果。

- 注意：只处理较低的 16 位。

```shell script
BitXor(Val1, Val2, [Val3, ...])
```

- 返回可变长度值列表的按位异或运算结果。

- 注意：只处理较低的 16 位。

```shell script
If(Cond, Val1, Val2)
```

- 如果 Cond 为 TRUE，则返回 Val1；否则返回 Val2。

```shell script
InRange(Val, Start, End)
```

- 如果 Min(Start,End) <= Val <= Max(Start,End)，则返回 TRUE。

```shell script
Not(Val)
```

- 返回 Val的逻辑取反运算结果。