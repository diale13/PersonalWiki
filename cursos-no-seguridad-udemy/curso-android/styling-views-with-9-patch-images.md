# Styling Views with 9 Patch Images

De momento si se cierra o sucede algo se ve al otro como anonimo, ademas que no se ve tan lindo



private void setChatRowAppearance\(boolean isItMe, ViewHolder holder\) {

```java
    if (isItMe) {
        holder.params.gravity = Gravity.END;
        holder.authorName.setTextColor(Color.GREEN);
        // If you want to use colours from colors.xml
        // int colourAsARGB = ContextCompat.getColor(mActivity.getApplicationContext(), R.color.yellow);
        // holder.authorName.setTextColor(colourAsARGB);

        holder.body.setBackgroundResource(R.drawable.bubble2);
    } else {
        holder.params.gravity = Gravity.START;
        holder.authorName.setTextColor(Color.BLUE);
        holder.body.setBackgroundResource(R.drawable.bubble1);
    }

    holder.authorName.setLayoutParams(holder.params);
    holder.body.setLayoutParams(holder.params);

}
```

Con ese diferenciamos si somos nosotros o el otro con quien chateamos.

![](../../.gitbook/assets/imagen%20%28899%29.png)

Se llaman .9 pues siguen esta convencion

{% embed url="https://developer.android.com/guide/topics/graphics/drawables\#nine-patch" %}

La gracia es que se pueden estirar para ser mas atractivas a la vista.

{% embed url="https://developer.android.com/studio/write/draw9patch.html" %}

![](../../.gitbook/assets/imagen%20%28880%29.png)



## EXTRA PERSIST USER



**The RegisterActivity**

Using [the code straight from the docs](https://firebase.google.com/docs/auth/android/manage-users#update_a_users_profile) we can save our username in the RegisterActivity like so:  


```text
private void saveDisplayName() {     FirebaseUser user = mAuth.getCurrentUser();    String displayName = mUsernameView.getText().toString();     if (user !=null) {        UserProfileChangeRequest profileUpdates = new UserProfileChangeRequest.Builder()                .setDisplayName(displayName)                .build();         user.updateProfile(profileUpdates)                .addOnCompleteListener(new OnCompleteListener<Void>() {                    @Override                    public void onComplete(@NonNull Task<Void> task) {                        if (task.isSuccessful()) {                            Log.d("FlashChat", "User name updated.");                        }                    }                });     } }
```

**The MainChatActivity**

Now that we no longer use the Shared Preferences, the MainChat Activity needs look towards Firebase for the username. We retrieve the logged in user and then call the getDisplayName\(\) method. 

```text
// TODO: Retrieve the display name from the Shared Preferencesprivate void setupDisplayName(){    FirebaseUser user = FirebaseAuth.getInstance().getCurrentUser();    mDisplayName = user.getDisplayName();}
```

