# [How to implement iMessage group sending?] iMessage is a free messaging application that comes with Apple devices (iPad, iPhone, iPod touch). Its messages are sent over the network, unlike carrier text messages.
1), Development (1 year) 2), Distribution (1 year) Ad Hoc App Store Ad Hoc packages can only run on the available devices registered in the account. Obviously, there is a limit of up to 100 devices. So the difference between these two Provisioning Profile files is that the device restrictions are different, and the Certificate they use is the same.
interface IMessage1 {

  The stack and some variables, but there is no separate address space between threads, and the thread has died. It is equal to the entire process, so multi-process programs are more powerful than multi-threaded programs, but it costs in the process. The resources are very large and the efficiency is poor. However, for certain requirements you can only use concurrent operations for certain variables. 4. What is the difference between stack and stack? Management method: For the stack, it is managed automatically by the compiler. There is no need to control it; for the heap, the release effort is controlled by the programmer and it is easy to generate a MemoryLeak. Application size: Stack: Under Windows, the stack is a data structure that extends to low addresses, which is a contiguous area of memory.

This statement means that the stack address and the maximum stack capacity are pre-specified by the system. Under Windows, the stack size is 2M (more statements are 1M, summarizing the constant size when constant is limited to the effective virtual memory in the computer system. It can be seen that the space obtained is flexible, it is relatively large.

NS_CLASS_AVAILABLE_IOS(2_0) @interface UINavigationBar : UIView <NSCoding, UIBarPositioning>

 

@property(nonatomic,assign) UIBarStyle barStyle;

@property(nullable,nonatomic,weak) id<UINavigationBarDelegate> delegate;

 

@property(nonatomic,assign,getter=isTranslucent) BOOL translucent NS_AVAILABLE_IOS(3_0) UI_APPEARANCE_SELECTOR; // Default is NO on iOS 6 and earlier. Always YES if barStyle is set to UIBarStyleBlackTranslucent(black transparent)

 

// Pushing a navigation item displays the item's title in the center of the navigation bar.

// The previous top navigation item (if it exists) is displayed as a "back" button on the left.

- (void)pushNavigationItem:(UINavigationItem *)item animated:(BOOL)animated;

//Push a pushNavigationItem into the stack of UINavigationBar.

 

- (nullable UINavigationItem *)popNavigationItemAnimated:(BOOL)animated;

//Pop up the UINavigationItem on the top of the UINavigationBar stack

// Returns the item that was popped.

 

@property(nullable, nonatomic,readonly,strong) UINavigationItem *topItem;

//Return to the top-level UINavigationItem control

 

@property(nullable, nonatomic,readonly,strong) UINavigationItem *backItem;

//Return to the UINavigationItem control under the topmost layer of the UINavigationItem control

 

@property(nullable,nonatomic,copy) NSArray<UINavigationItem *> *items;

//Return multiple UINavigationItem controls contained in UINavigationBar

 

- (void)setItems:(nullable NSArray<UINavigationItem *> *)items animated:(BOOL)animated;

//Set multiple UINavigationItem controls for UINavigationBar at the same time

// If animated is YES, then simulate a push or pop depending on whether the new top item was previously in the stack.

 

@property(null_resettable, nonatomic,strong) UIColor *tintColor;//Coloring

 

@property(nullable, nonatomic,strong) UIColor *barTintColor NS_AVAILABLE_IOS(7_0) UI_APPEARANCE_SELECTOR; //Navigation bar coloring default is nil

 

- (void)setBackgroundImage:(nullable UIImage *)backgroundImage forBarPosition:(UIBarPosition)barPosition barMetrics:(UIBarMetrics)barMetrics NS_AVAILABLE_IOS(7_0) UI_APPEARANCE_SELECTOR;

//Sets the background image to use for a given bar position and set of metrics. Official annotation: Sets the background image to use for a given bar position and set of metrics.

 

- (nullable UIImage *)backgroundImageForBarPosition:(UIBarPosition)barPosition barMetrics:(UIBarMetrics)barMetrics NS_AVAILABLE_IOS(7_0) UI_APPEARANCE_SELECTOR;

//Get the background image through the navigation bar position and measurement

 

- (void)setBackgroundImage:(nullable UIImage *)backgroundImage forBarMetrics:(UIBarMetrics)barMetrics NS_AVAILABLE_IOS(5_0) UI_APPEARANCE_SELECTOR;

//Set the background image through the navigation bar measurement

 

- (nullable UIImage *)backgroundImageForBarMetrics:(UIBarMetrics)barMetrics NS_AVAILABLE_IOS(5_0) UI_APPEARANCE_SELECTOR;

//Get the background image through the navigation bar measurement

 

@property(nullable, nonatomic,strong) UIImage *shadowImage NS_AVAILABLE_IOS(6_0) UI_APPEARANCE_SELECTOR;//shadow image

 

@property(nullable,nonatomic,copy) NSDictionary<NSString *,id> *titleTextAttributes NS_AVAILABLE_IOS(5_0) UI_APPEARANCE_SELECTOR;//Title text attributes

 

- (void)setTitleVerticalPositionAdjustment:(CGFloat)adjustment forBarMetrics:(UIBarMetrics)barMetrics NS_AVAILABLE_IOS(5_0) UI_APPEARANCE_SELECTOR;

- (CGFloat)titleVerticalPositionAdjustmentForBarMetrics:(UIBarMetrics)barMetrics NS_AVAILABLE_IOS(5_0) UI_APPEARANCE_SELECTOR;

//Adjust the vertical position of the title

 

@property(nullable,nonatomic,strong) UIImage *backIndicatorImage NS_AVAILABLE_IOS(7_0) UI_APPEARANCE_SELECTOR;

//Background indicator picture

 

@property(nullable,nonatomic,strong) UIImage *backIndicatorTransitionMaskImage NS_AVAILABLE_IOS(7_0) UI_APPEARANCE_SELECTOR;

//The image used as a mask for content during push and pop transitions.——Mask image used as push and pop transitions

 

@end

Fragmentation problem: For piles, frequent new/deletion will inevitably lead to discontinuous memory space, resulting in a large amount of fragmentation, which reduces program efficiency. For the stack, there is no such problem because the stack is the first queue and it is one of them, so it will never have the memory block from the middle of the stack.

Assignment: The heap is dynamically allocated, there is no static allocation of the stack. There are two types of allocation: static allocation and dynamic allocation. Static allocation is a compiler completion, such as a deflection variable. AlloCA function allocates dynamic allocation, but dynamic allocation and stack stack are different. His dynamic allocation is issued by the compiler without implementing it.

Allocation efficiency: The stack is a data structure provided by the machine system. The computer provides support in the underlying stack: the address of the stack is allocated, and the stack within the stack has special instructions that determine the efficiency of the stack. . The stack is provided by the C/C++ function library, and its mechanism is very complex. 5. Object-c memory management? When you create an object using the new Alloc Replication method, and the object's retain count has a retain counter value of 1 and is set to autorelease, you do not need to do anything to ensure that the object is cleared. If completed during this object, you need to retain it and ensure the operation completes. If you have retained objects, you need to (eventually) release or autorelease the objects. You must keep the number of reserved methods and used methods.

     void print();

 

     default void getMsg(){

         /*

         It is a common method, only available after jdk1.8

         */

         System.out.println("I am a normal method of interface 1");

     }

     static void getMss(){

         System.out.println("I am a static method of interface 1");

     }

}

 

class MessageImpl1 implements IMessage1{

 

     @Override

     public void print() {

         System.out.println(this.getClass().getName());

     }

    

}

 

public static void main (String[] args){

         IMessage1 iMessa