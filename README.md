MRSwipeTableViewCell
--------------------

A `UITableViewCell` that allow swipe left to reveal a background view with parallax effect.
See [gift](https://github.com/martinezdelariva/MRSwipeTableViewCell/blob/master/video.gif).


## API Reference
Please refer to the header file [`MRSwipeTableViewCell.h`] for a complete overview of the capabilities of the class.

## Installation

Copy files `MRSwipeTableViewCell.h` and `MRSwipeTableViewCell.m` into your project.

## Usage

- Subclass `MRSwipeTableViewCell`;
- Add to forward content to `centerContentView` property.
- Add to background content to `rightContentView` property.

```objc
- (id)initWithStyle:(UITableViewCellStyle)style reuseIdentifier:(NSString *)reuseIdentifier
{
    self = [super initWithStyle:style reuseIdentifier:reuseIdentifier];
    if (self) {        
        // Content view
        [self.centerContentView addSubview:[self.customFrontView];
        [self.rightContentView addSubview:self.customRightView];
    }
    
    return self;
}
```

- Implement protocol `MRSwipeTableViewCellProtocol`.

```objc
@protocol MRSwipeTableViewCellProtocol <NSObject>

// Right view width.
- (float)rightWidth;

// Parallax width. Value must the beetween 0 and rightWidth:
- (float)rightParallaxWidth;
```

### Delegation

`MRSwipeTableViewCell` has a set of delegate methods in order to track the user behaviors. Take a look at the header file to be aware of all the methods provided by `MRSwipeTableViewCellDelegate`.

```objc
@protocol MRSwipeCellDelegate <NSObject>
@optional
- (void)didShowRightView:(MRSwipeTableViewCell *)cell;
- (void)didHideRightView:(MRSwipeTableViewCell *)cell;
@end
```


## Requirements

- iOS >= 7.0
- ARC


## License

// TODO