

BASIC USAGE

        func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        
        window = UIWindow(frame: UIScreen.main.bounds)
        
        let vc1 = OnlineViewController()
        let vc2 = MessageViewController()
        let vc3 = GroupViewController()
        let viewControllers = [vc1,vc2,vc3]
        
        let tabViews = [TabPageView(title: "Online", image: "online"),
                        TabPageView(title: "Message", image: "message"),
                        TabPageView(title: "Group", image: "group")]
        
        let option = PageViewOption()
        option.tabViewHeight = 65
        option.tabViewTextFont = UIFont.boldSystemFont(ofSize: 15)
        option.tabStyle = .imageWithText
        option.imageHeight = 25
        option.indicatorViewHeight = 2
        option.backgroundDefaultColor = UIColor(white: 0.97, alpha: 0.98)
        
        let pageVC = PageViewController(viewControllers: viewControllers, tabViews: tabViews, option: option)
        pageVC.title = "Trang chủ"
        
        let naviVC = UINavigationController(rootViewController: pageVC)
        naviVC.navigationBar.shadowImage = UIImage()
        
        //window?.rootViewController = pageVC
        window?.rootViewController = naviVC
        window?.makeKeyAndVisible()
        window?.backgroundColor = .white
        return true
    }
