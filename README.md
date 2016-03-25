# HJProgressView
http://stackoverflow.com/questions/22311516/uiprogressview-custom-track-and-progress-images-in-ios-7-1
主要功能：
1.修复UIProgressView在iOS7，iOS8.3上设置trackimage和ProgressImage无效Bug
2.UIProgressView设置进度圆角

用法示例
```obj
#define RGBCOLOR(r,g,b) [UIColor colorWithRed:(r)/255.0f green:(g)/255.0f blue:(b)/255.0f alpha:1]
- (void)viewDidLoad {
    [super viewDidLoad];
    // Do any additional setup after loading the view, typically from a nib.
    
    UIProgressView *progressView=[[UIProgressView alloc]initWithProgressViewStyle:UIProgressViewStyleDefault];
    progressView.frame=CGRectMake([UIScreen mainScreen].bounds.size.width/2-150, 50, 300, 50);
    [progressView setProgress:0.68 animated:YES];
    
    progressView.transform=CGAffineTransformMakeScale(1.0, 8.0);//默认为2px，无法通过frame设置高度
    [self.view addSubview:progressView];
    [progressView setRadiusTrackColor:RGBCOLOR(231, 233, 238) progressColor:RGBCOLOR(255, 153,0)];
}

```