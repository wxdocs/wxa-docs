-  API:

   -  渲染: 画布 wx.createCanvas Canvas RenderingContext
      Canvas.getContext Canvas.toTempFilePath Canvas.toDataURL
      Canvas.toTempFilePathSync 图片 wx.createImage Image 字体
      wx.getTextLineHeight wx.loadFont 帧率
      wx.setPreferredFramesPerSecond cancelAnimationFrame
      requestAnimationFrame
   -  系统 生命周期 wx.exitMiniProgram wx.getLaunchOptionsSync wx.onHide
      wx.offHide wx.onShow wx.offShow 系统信息 wx.getSystemInfo
      wx.getSystemInfoSync 系统事件 wx.onAudioInterruptionEnd
      wx.offAudioInterruptionEnd wx.onAudioInterruptionBegin
      wx.offAudioInterruptionBegin wx.onError wx.offError 触摸事件
      wx.onTouchStart wx.offTouchStart wx.onTouchMove wx.offTouchMove
      wx.onTouchEnd wx.offTouchEnd wx.onTouchCancel wx.offTouchCancel
      Touch
   -  设备 加速计 wx.onAccelerometerChange wx.startAccelerometer
      wx.stopAccelerometer 电量 wx.getBatteryInfo wx.getBatteryInfoSync
      剪贴板 wx.getClipboardData wx.setClipboardData 罗盘
      wx.onCompassChange wx.startCompass wx.stopCompass 网络
      wx.getNetworkType wx.onNetworkStatusChange 屏幕
      wx.getScreenBrightness wx.setKeepScreenOn wx.setScreenBrightness
      振动 wx.vibrateShort wx.vibrateLong
   -  文件 wx.getFileSystemManager FileSystemManager Stats
      FileSystemManager.access FileSystemManager.accessSync
      FileSystemManager.copyFile FileSystemManager.copyFileSync
      FileSystemManager.getFileInfo FileSystemManager.getSavedFileList
      Stats.isDirectory Stats.isFile FileSystemManager.mkdir
      FileSystemManager.mkdirSync FileSystemManager.removeSavedFile
      FileSystemManager.readFile FileSystemManager.rename
      FileSystemManager.rmdir FileSystemManager.readdir
      FileSystemManager.readdirSync FileSystemManager.renameSync
      FileSystemManager.rmdirSync FileSystemManager.readFileSync
      FileSystemManager.saveFile FileSystemManager.stat
      FileSystemManager.saveFileSync FileSystemManager.statSync
      FileSystemManager.unlink FileSystemManager.unzip
      FileSystemManager.unlinkSync FileSystemManager.writeFile
      FileSystemManager.writeFileSync
   -  位置 wx.getLocation
   -  网络
   -  开放接口 登录 wx.checkSession wx.login code2accessToken 授权
      wx.authorize 用户信息 wx.getUserInfo UserInfo 设置 wx.getSetting
      wx.openSetting AuthSetting 微信运动 wx.getWeRunData 开放数据
      wx.getFriendCloudStorage wx.getGroupCloudStorage
      wx.getUserCloudStorage wx.getUserInfo wx.removeUserCloudStorage
      wx.setUserCloudStorage KVData UserGameData removeUserStorage
      setUserStorage 开放数据域 wx.getOpenDataContext wx.onMessage
      OpenDataContext OpenDataContext.postMessage 接口调用凭证
      getAccessToken
   -  转发 wx.getShareInfo wx.hideShareMenu wx.onShareAppMessage
      wx.offShareAppMessage wx.showShareMenu wx.shareAppMessage
      wx.updateShareMenu
   -  调试 wx.setEnableDebug
   -  数据缓存 wx.clearStorage wx.clearStorageSync wx.getStorage
      wx.getStorageInfo wx.getStorageSync wx.getStorageInfoSync
      wx.removeStorage wx.removeStorageSync wx.setStorage
      wx.setStorageSync
   -  界面 交互 wx.hideToast wx.hideLoading wx.showModal wx.showToast
      wx.showLoading wx.showActionSheet 键盘 wx.hideKeyboard
      wx.onKeyboardInput wx.offKeyboardInput wx.onKeyboardConfirm
      wx.offKeyboardConfirm wx.onKeyboardComplete wx.offKeyboardComplete
      wx.showKeyboard 菜单 wx.setMenuStyle 状态栏 wx.setStatusBarStyle
      窗口 wx.onWindowResize wx.offWindowResize
   -  更新 wx.getUpdateManager UpdateManager UpdateManager.applyUpdate
      UpdateManager.onCheckForUpdate UpdateManager.onUpdateReady
      UpdateManager.onUpdateFailed
   -  Worker wx.createWorker Worker Worker.onMessage Worker.postMessage
      Worker.terminate
   -  媒体 音频 wx.createInnerAudioContext InnerAudioContext
      InnerAudioContext.destroy InnerAudioContext.offCanplay
      InnerAudioContext.onPause InnerAudioContext.onStop
      InnerAudioContext.offStop InnerAudioContext.onEnded
      InnerAudioContext.offEnded InnerAudioContext.onTimeUpdate
      InnerAudioContext.onPlay InnerAudioContext.onError
      InnerAudioContext.offPause InnerAudioContext.onWaiting
      InnerAudioContext.offWaiting InnerAudioContext.onSeeking
      InnerAudioContext.offSeeking InnerAudioContext.onSeeked
      InnerAudioContext.offSeeked InnerAudioContext.offPlay
      InnerAudioContext.offTimeUpdate InnerAudioContext.onCanplay
      InnerAudioContext.offError InnerAudioContext.pause
      InnerAudioContext.pause InnerAudioContext.play
      InnerAudioContext.seek 录音 wx.getRecorderManager RecorderManager
      RecorderManager.onPause RecorderManager.onStop
      RecorderManager.onFrameRecorded RecorderManager.onError
      RecorderManager.onStart RecorderManager.pause
      RecorderManager.resume RecorderManager.stop RecorderManager.start
      图片 wx.chooseImage wx.previewImage wx.saveImageToPhotosAlbum
      ImageFile 视频 wx.createVideo wx.createVideo Video Video
      Video.exitFullScreen Video.exitFullScreen Video.offPause
      Video.onEnded Video.offEnded Video.onTimeUpdate
      Video.offTimeUpdate Video.onError Video.offError Video.onPlay
      Video.offError Video.onError Video.offTimeUpdate
      Video.onTimeUpdate Video.onPause Video.offWaiting Video.onWaiting
      Video.offPlay Video.offWaiting Video.onPlay Video.offPlay
      Video.onPause Video.offPause Video.onEnded Video.offEnded
      Video.onWaiting Video.pause Video.play Video.pause Video.play
      Video.requestFullScreen Video.requestFullScreen Video.seek
      Video.stop Video.seek Video.stop
   -  性能 wx.getPerformance wx.triggerGC Performance Performance.now
   -  定时器 clearTimeout clearInterval setTimeout setInterval
   -  虚拟支付 wx.requestMidasPayment midasCancelPay midasGetBalance
      midasPay midasPresent
