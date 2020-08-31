### Family Management

Create and query family information change monitor

#### Destruction

**Declaration**

```java
void onDestroy()
```

**Example**

```java
TuyaHomeSdk.getHomeManagerInstance().onDestroy();
```

#### Create family

**Declaration**

```java
void createHome(String name, double lon, double lat, String geoName, List rooms, ITuyaHomeResultCallback callback)
```

**Parameters**

| Parameters | Description |
| :--- | :--- |
| name | Family name |
| lon | longitude |
| lat | latitude |
| geoName | Home location name |
| rooms | Room list |
| callback | Result callback |

**Example**

```java
TuyaHomeSdk.getHomeManagerInstance().createHome(name, lon, lat, geoName, rooms, new ITuyaHomeResultCallback() {
        @Override
        public void onError(String errorCode, String errorMsg) {
            // do something
        }
        @Override
        public void onSuccess(HomeBean bean) {
            // do something
        }
    });
```

#### Get Family List

**Declaration**

```java
void queryHomeList(ITuyaGetHomeListCallback callback)
```

**Parameters**

| Parameters | Description |
| :--- | :--- |
| callback | Result callback |

**Example**

```java
TuyaHomeSdk.getHomeManagerInstance().queryHomeList(new ITuyaGetHomeListCallback() {
        @Override
        public void onError(String errorCode, String error) {
            // do something
        }
        @Override
        public void onSuccess(List<HomeBean> homeBeans) {
            // do something
        }
    });
```

#### Change of Registered Family Information

There are: addition and deletion of family, information change, change of sharing list and successful monitoring of server connection

**Declaration**

```java
void registerTuyaHomeChangeListener(ITuyaHomeChangeListener listener)
```

**Parameters**

| Parameters | Description |
| :--- | :--- |
| listener | Monitor |

**Example**

```java
// define a listener
ITuyaHomeChangeListener listener = new ITuyaHomeChangeListener() {
        @Override
        public void onHomeInvite(long homeId, String homeName) {
            // do something
        }
        @Override
        public void onHomeRemoved(long homeId) {
            // do something
        }
        @Override
        public void onHomeInfoChanged(long homeId) {
            // do something
        }
        @Override
        public void onSharedDeviceList(List<DeviceBean> sharedDeviceList) {
            // do something
        }
        @Override
        public void onSharedGroupList(List<GroupBean> sharedGroupList) {
            // do something
        }
        @Override
        public void onServerConnectSuccess() {
            // do something
        }
        @Override
        public void onHomeAdded(long homeId) {
            // do something
        }
    };
// register a listener
TuyaHomeSdk.getHomeManagerInstance().registerTuyaHomeChangeListener(listener);
```

#### Change of Cancellation Family Information

**Declaration**

```java
void unRegisterTuyaHomeChangeListener(ITuyaHomeChangeListener listener)
```

**Parameters**

| Parameters | Description |
| :--- | :--- |
| listener | Monitor |

**Example**

```java
// define a listener
ITuyaHomeChangeListener listener = new ITuyaHomeChangeListener() {
        @Override
        public void onHomeInvite(long homeId, String homeName) {
            // do something
        }
        @Override
        public void onHomeRemoved(long homeId) {
            // do something
        }
        @Override
        public void onHomeInfoChanged(long homeId) {
            // do something
        }
        @Override
        public void onSharedDeviceList(List<DeviceBean> sharedDeviceList) {
            // do something
        }
        @Override
        public void onSharedGroupList(List<GroupBean> sharedGroupList) {
            // do something
        }
        @Override
        public void onServerConnectSuccess() {
            // do something
        }
        @Override
        public void onHomeAdded(long homeId) {
            // do something
        }
    };
// register a listener
TuyaHomeSdk.getHomeManagerInstance().registerTuyaHomeChangeListener(listener);
// ...
// unregister a listener
TuyaHomeSdk.getHomeManagerInstance().unRegisterTuyaHomeChangeListener(listener);
```


