檔案架構:
　　-code
　　　　－code.ipynb : 可以依序執行此檔案的執行方塊，就可以得到最後的result.png
　　-data
　　　　-bonus_imgs : 放置實作bonus(recognizing panoromas)所需要用到的圖片
　　　　-bonus_warped : 將實作bonus(recognizing panoromas)所產生的warped.npy存檔於此
　　　　-imgs : 將實作image stitching 所需要用到的圖片放置於此
　　　　-warped : 由於cylindrical warping很花時間，因此會將warp的結果存放於此，避免下次還要再跑一次 
　　-plot : 放置實驗的結果
　　-result : 放置image stitching產生的結果與過程
       -bonus_result : 放置含有bonus的image stitching產生的結果與過程

執行方式:
直接打開code.ipynb即可依照順序執行裡面的內容
若要修改參數可在最底下的config調整
若要跑有bonus的演算法，將"bonus"設為True，跑一般的演算法則設為False
執行完所有的執行方塊，便能從bonus_result或result資料夾看到產生的結果bonus_result.png/result.png
　　
config = {
    "path" : base_path,				                 #各個資料夾外層的路徑
    "input_dirpath": base_path+"data/imgs/",                                             #將實作image stitching 所需要用到的圖片放置於此
    "warp_dirpath": base_path+'data/warped/',			 #將warp的結果存放於此
    "plot_dirpath": base_path+'plot/',                                                         #放置實驗的結果
    "result_path": base_path+'result/',                                                         #放置image stitching產生的結果與過程
    "bonus_result_path": base_path+'bonus_result/',                                  #放置含有bonus的image stitching產生的結果與過程
    "bonus_input_dirpath": base_path+'data/bonus_imgs/',                       #放置實作bonus(recognizing panoromas)所需要用到的圖片
    "bonus_warp_dirpath": base_path+'data/bonus_warped/',                  #將實作bonus(recognizing panoromas)所產生的warped.npy存檔於此
    "bonus": True,						#是否使用含有bonus的演算法
    "use_warp_cache":True,					#是否使用warp的npy檔
    "non_maximal": True,					#是否啟用non-maximal suppresion
    "window":40,						#描述特徵點所用到的window大小
    "window_size":3,						#gaussian blur的kernel size
    "num_features":1500,					#最後將多少feature拿去算pairs
    "sobel": True,						#使用sobel filter或gradient算corner response
    "local_max": True,						#是否使用local max過濾掉一些可能的特徵點
    "threshold_ratio": 0.01,					#特徵點的threshold
    "sigma": 1,						#gaussian blur的sigma
    "c_robust": 1,						#non-maximal suprresion論文內提到的c_robust
    "k":0.04,						#corner response的k
    "threshold_clip":False,
    "threshold_bound":1e8,
    "print": False
}
　　