# myscan  支持二维码，条形码通用扫描

在项目gradle中compile 'com.github.XuDaojie:QRCode-Android:v0.4.2'即可使用

直接跳转：

Intent i = new Intent(MainActivity.this, CaptureActivity.class); 

MainActivity.this.startActivityForResult(i, REQUEST_CODE);

然后回调拿到值即可：

    @Override
    
    protected void onActivityResult(int requestCode, int resultCode, Intent data) {
    
        super.onActivityResult(requestCode, resultCode, data);
        
        if (resultCode == RESULT_OK
                && requestCode == REQUEST_CODE
                && data != null) {
                
            String result = data.getStringExtra("CODE");
            
            Toast.makeText(MainActivity.this, result, Toast.LENGTH_SHORT).show();
            
        }
        
    }
    
