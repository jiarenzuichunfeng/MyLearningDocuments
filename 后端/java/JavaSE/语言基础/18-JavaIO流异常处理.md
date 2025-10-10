# 18-JavaIO流异常处理

* 1.6

```
 public static void ReadImage(String dir,String trgdir) {
        BufferedInputStream bis = null;
        try {
            FileInputStream fis = new FileInputStream(dir);
            bis = new BufferedInputStream(fis);

            FileOutputStream fos = new FileOutputStream(trgdir);
            BufferedOutputStream bos = new BufferedOutputStream(fos);


            int size;
            byte[] buffer = new byte[1024];

            while ((size = bis.read(buffer)) != -1) {
                bos.write(buffer, 0, size);
            }
        } catch (IOException e) {
            throw new RuntimeException(e);
        } finally {
            if (bis != null) {
                try {
                    bis.close();
                } catch (IOException e) {
                    throw new RuntimeException(e);
                }finally {
                    if (bos != null){
                        try {
                            bos.close();
                        }catch (IOException e) {
                            throw new RuntimeException(e);
                            }
                    }
                }
            }
        }
    }
```

* 1.7

  ```
  public static void copy(File from, File to) {
     try ( FileInputStream fis = new FileInputStream(from);
           BufferedInputStream bis = new BufferedInputStream(fis);
  
           FileOutputStream fos = new FileOutputStream(to);
           BufferedOutputStream bos = new BufferedOutputStream(fos);
           ) {
         int size;
         byte[] buffer = new byte[1024];
  
         while ((size = bis.read(buffer)) != -1) {
             bos.write(buffer, 0, size);
         }
     } catch (Exception e) {
        e.printStackTrace();
     } 
  }
  ```