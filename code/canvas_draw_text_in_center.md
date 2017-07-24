```java
//初始化
String mText = "Ugf32fA";
int mTextColor = Color.BLACK;
int mTextSize = 100;

Paint mPaint = new Paint();
mPaint.setTextSize(mTextSize);
mPaint.setColor(mTextColor);
//创建文本绘制的矩形区域
Rect mBound = new Rect();
//获取文本绘制区域，参数：文本，起始处，结束处，区域
mPaint.getTextBounds(mText, 0, mText.length(), mBound);


Paint.FontMetricsInt fontMetrics = mPaint.getFontMetricsInt();
//baseline计算方式：画布高度的一半 - 文字总高度的一半
int baseline = (getMeasuredHeight()) / 2 - (fontMetrics.top+fontMetrics.bottom)/2;
//绘制文字
canvas.drawText(mText, getWidth() / 2 - mBound.width() / 2, baseline, mPaint);
```