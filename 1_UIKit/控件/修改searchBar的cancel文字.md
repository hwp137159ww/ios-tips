## 修改SearchBar的Cancel Button 的Title


````objc 
//  注意点：
//       使用iOS8 SDK ，本次 UISearchBar适用于iOS7(+)版本，如果想要适配iOS6，则需要对应适配iOS6.
//  例如：
//      iOS7+ :     for(id cc in [searchBar.subviews[0] subviews]){}
//      iOS7- :     for(id cc in [searchBar subviews]){}
//  
///#end

- (void)searchBarTextDidBeginEditing:(UISearchBar *)searchBar
{
    for(id cc in [searchBar.subviews[0] subviews])
    {
        if([cc isKindOfClass:[UIButton class]])
        {
            UIButton *btn = (UIButton *)cc;
            [btn setTitle:[AppLanguageProcess getLanguageWithKey:@"TEXT_CANCEL"]  forState:UIControlStateNormal];
            [btn setTitleColor:[UIColor whiteColor] forState:UIControlStateNormal];
        }
    }
} 

````
