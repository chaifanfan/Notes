Date 02/10/2021
##### Different scenarios of using react native navigation

Before using React Navigation 5, make sure to read this article: [upgrading-from-4.x](https://reactnavigation.org/docs/upgrading-from-4.x/)  

**Scenarios:**

1. Pass params when creating bottom navigation  
   Use initialParams prop on Screen. Use route.params access screen's params.  

       <Stack.Screen
         name="Profile"
         component="ProfileScreen"
         initialParams={{userId: user.id}}
       />

       function ProfileScreen({route}) {
         const {userId} = route.params
       }

**Reference:**  
https://reactnavigation.org/docs/upgrading-from-4.x/