# Testing expo-dev-client with EAS Update

1. Created a project with `expo init` (Expo CLI version 5.0.3).
2. Ran `expo install expo-dev-client`, which installed version 0.8.0.
3. Ran `expo install expo-updates`, which installed version 0.11.3.
4. Ran `eas build:configure` (EAS CLI version 0.43.0).
5. Ran `eas update:configure` (I am currently logged in with my personal account (`eas whoami`)).
6. Ran `eas device:create` to register my phone with this app so that i can make an internal distribution build of it.
7. Ran `eas build --profile development --platform ios`, since I have an iPhone.
8. Ran the build on my device to make sure it worked.
9. Then, changed the text in **App.tsx** to "Hello world 1".
10. Ran `eas update --branch test-branch --message "hello world 1"`.
11. Then manually constructed this URL:

    ```
    exp+test-expo-dev-client-eas-update://expo-development-client/?url=https://u.expo.dev/4dae2e69-fde1-44e8-8dc7-8e1c2ea2af2d?channel-name=test-branch
    ```

12. Created a QR code with https://www.qr-code-generator.com/, then scanned it with my phone.
13. Saw the "Hello world 1" appear inside the development build of the app.
14. To make sure this works with other channels/branches, I changed the text to "Hello world 2".
15. Then ran `eas update --branch test-branch-2 --message "update 2"`
16. Then updated the URL to:

    ```
    exp+test-expo-dev-client-eas-update://expo-development-client/?url=https://u.expo.dev/4dae2e69-fde1-44e8-8dc7-8e1c2ea2af2d?channel-name=test-branch-2
    ```

17. Made a QR code again and scanned it, then saw "Hello world 2".

Here's a video of steps 9 - 17:

https://user-images.githubusercontent.com/6455018/148657554-c150378c-4d84-4dd3-b64e-857584affe98.mp4
