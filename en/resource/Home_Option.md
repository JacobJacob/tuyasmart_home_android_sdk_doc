## Operation Class of Home

The ITuyaHome provides the operation class for the home, and ithandle the data of home and information update.  The ITuyaHome needs to use the `TuyaHomeSdk.newHomeInstance(homeId)` for initiation. 

## **Initiate All Data of Home**
```java
/**
 * Obtain all information for home from cloud
 * @param callback
 */
void getHomeDetail(ITuyaHomeResultCallback callback);
```
## Obtain All Data in the Cache.
```java
/**
 * Obtain all information for home from cache
 * @param callback
 */
void getHomeLocalCache(ITuyaHomeResultCallback callback);
```
## Update Home Information
```java
/**
 * Update the home information
 *
 * @param name     Name of home
 * @param lon      Longitude of current home
 * @param lat      Latitude of current home
 * @param geoName  Geographic position
 * @param callback
 */
void updateHome(String name, double lon, double lat, String geoName, IResultCallback callback);
```
## Dismiss home
```java
/**
 * Dismiss home
 *
 * @param callback
 */
void dismissHome(IResultCallback callback);
```

## Sort
```java
/**
 * Sort
 *
 * @param idList homeId list 
 * @param callback
 */
void sortHome(List<Long> idList, IResultCallback callback);
```
## Add room
```java
/**
 * Add room
 *
 * @param name
 * @param callback
 */
void addRoom(String name, ITuyaRoomResultCallback callback);
```
## Remove room of a home
```java
 /**
 * Remove room
 *
 * @param roomId
 * @param callback
 */
void removeRoom(long roomId, IResultCallback callback);

```

## Sort rooms of a home
```java
/** Sort rooms
*
* @param idList   id list of rooms
* @param callback
*/
void sortRoom(List<Long> idList, IResultCallback callback);
```
## Query room list
```java
/**
 * Query room list
 * @param callback
 */
void queryRoomList(ITuyaGetRoomListCallback callback);
```
## Create Group
```java
/**
 * Create group
 *
 * @param productId  Product ID
 * @param name      Name of group
 * @param devIdList  Device ID List
 * @param callback
 */
void createGroup(String productId, String name, List<String> devIdList, final ITuyaResultCallback<Long> callback);
```
## Query Room Information based on Devices
```java
/**
 * Query room information based on devices
 *
 * @param deviceList
 * @return
 */
List<RoomBean> queryRoomInfoByDevice(List<DeviceBean> deviceList);
```
## Monitor the Information Change of Home
```java
/**
 * Monitor the information change of home (add or remove devices)
 *
 * @param listener
 */
void registerHomeStatusListener(ITuyaHomeStatusListener listener); 
   
public interface ITuyaHomeStatusListener {
    /**
     * Add devices
     * @param devId
     */
    void onDeviceAdded(String devId);
    /**
     * Remove devices
     * @param devId
     */
    void onDeviceRemoved(String devId);
}
```
## Deregister the Monitoring of Information Change of a Home
```java
/** Deregister the monitoring of information change of a home
*
* @param listener
*/
void unRegisterHomeStatusListener(ITuyaHomeStatusListener listener);
```
## Destroy
```java
void onDestroy();
```