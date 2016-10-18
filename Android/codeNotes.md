##烂笔头


####代码

`//dialog的返回键监听       
 dialog.setOnKeyListener(new DialogInterface.OnKeyListener() {
//            @Override
//            public boolean onKey(DialogInterface dialog, int keyCode,
//                                 KeyEvent event) {
//                if (keyCode == KeyEvent.KEYCODE_BACK
//                        && event.getRepeatCount() == 0) {
//                    adapter.valueUpdate(mViewPager.getCurrentItem(), facevalue,"");
//                }
//                return false;
//            }
//        });   

// 设置点击屏幕Dialog不消失   
dialog.setCanceledOnTouchOutside(false);
dialog.setCancelable(false);
`
