---
mark_as_read:
    updated_at: 2024-03-24 17:00:00+03:00
---

# Lab 7: User tracking

Track user sessions and log the username

## Task 1: Configuration

1. Navigate to: **Tracking** -> **User Tracking** and click ![+ Create New](create-new.png)

    ![Create New User Tracking](user-tracking-create-new.png)

1. Name the policy **DVWA_User_Tracking_Policy**, click ![OK](ok.png) then ![+ Create New](create-new.png) 

    ![Lab5 ut img4](Lab5-ut-img4.png)

1. Expand **User Tracking Rule** dropbox and click **Create**

1. Enter the following values and click ![OK](ok.png)

    | Field              | Value                   |
    |--------------------|-------------------------|
    | Name               | DVWA_User_Tracking_Rule |
    | Authentication URL | /login.php              |
    | Username           | username                |
    | Password           | password                |
    | Session ID Name    | PHPSESSID               |
    | Logoff Path        | /logout.php             |

    ![Lab5 ut img2](Lab5-ut-img2.png)

1. Select the rule created and click ![OK](ok.png)

    ![Lab5 ut img5](Lab5-ut-img5.png)

1. Navigate to: **Tracking** -> **User Tracking** click **User Tracking Rule**, select **DVWA_User_Tracking_Rule** and click ![Edit](edit.png)

    ![Lab5 ut img12](Lab5-ut-img12.png)

1. Click ![+ Create New](create-new.png)

    ![Lab5 ut img3](Lab5-ut-img3.png)

1. Click ![OK](ok.png)

1. Navigate to: **Policy** -> **Server Policy** -> and edit **DVWA_server_policy**

1. Select **WP_DVWA** profile and click the ![Pencil](pencil.png)

1. Select **Standard Protection** under **Signatures**

    ![Lab5 ut img7](Lab5-ut-img7.png)

1. Scroll down to **User Tracking** and select **DVWA_User_Tracking_Policy**. Click ![OK](ok.png)

    ![Lab5 ut img6](Lab5-ut-img6.png)

## Task 2: Results

1. Open DVWA

1. If logged in, click **Logout** in bottom left

1. Login using one of the users below:

    | Username | Password |
    |----------|----------|
    | gordonb  | abc123   |
    | pablo    | letmein  |
    | smithy   | password |

1. In DVWA on the left menu click **Command Injection**

1. Under **Enter an IP address** type the following and click Submit

    ```bash
    ;ls -la
    ```

    ![Lab5 ut img8](Lab5-ut-img8.png)

1. FortiWeb blocks the request

    ![Lab5 ut img9](Lab5-ut-img9.png)

1. Navigate to: **Log & Report** -> **Log Access** -> **Attack**

1. Right-click **URL**, and scroll down to select **Username**, and then click **Apply**

    ![Lab5 ut img10](Lab5-ut-img10.png)

1. The Username is displayed in the logs

    ![Lab5 ut img11](Lab5-ut-img11.png)

 !!! tip
        Check your CTF :)