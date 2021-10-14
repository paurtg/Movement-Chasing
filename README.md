# Raycast Shooting

## 1. Character movement

In order to shoot, firstly we need to add movement to our character. Using the same project from the last tutorial, I will create a new script called Movement. We will need to add a ``public float speed`` so we are able to edit the object's speed in the inspector. In Update we need to write a ``transform.Translate`` statement indicating the ``Horizontal`` and ``Vertical`` axis. I multiplied it by deltaTime more than usual just to make it a bit faster but it is not needed. 

It should look like this:

![Capture](https://user-images.githubusercontent.com/91539042/137241289-eb306951-9eac-40de-8aab-2fd59f9e6c17.PNG)

Last time we made a character to patrol between different waypoints, now we are going to make them chase us.

## 2. Chasing script

Create a new script, call it FollowAi. We will need a ``public Transform target`` that will represent our main character and another ``public Transform myTransform`` which will  represent current transform data of the enemy itself. 

![eee](https://user-images.githubusercontent.com/91539042/137243405-73ac1cfb-1456-4d8b-8e2e-05d093f19d50.PNG)

In ``void Update`` we will need a statement that will direct the enemy to look at us when it is chasing us, for this we will need to write a ``transform.LookAt`` statement. 
Finally, we will need to tell the enemy to move and we will need to indicate its speed with a simple ``transform.Translate`` statement.

It should look like this:

![eee](https://user-images.githubusercontent.com/91539042/137243795-0963e206-1de4-4e3b-89bd-d4b881b9829f.PNG)

This will make the enemy follow us straight away, but we actually want it to follow us when we are in its range. To do this we will need to do some modifications.

## 3. Chasing if in range

We will add a ``int MoveSpeed`` to specify the speed of our enemy, a ``int MaxDist`` meaning the range the target will be detected and a ``int MinDist``, to specify the minimun range the target will be detected.

![ssssssssssss](https://user-images.githubusercontent.com/91539042/137247938-451f9e63-f74d-4dfe-afe1-f50ca63a2a6a.PNG)

In Update, we will need to write two ``if`` statements, to tell the enemy to follow us when we are within the range and to stop following us when we are out of range. This values can be adjustable to our liking.

The code in Update should look like this:

![ddddd](https://user-images.githubusercontent.com/91539042/137248093-b4668b6d-f4ea-46f4-b88c-46469dcd0a8c.PNG)

## 4. Test it

Go to the inspector, attach the script ``FollowAi`` to our enemy and in Target (in the inspector from the script) drag the main character and in ``Move Speed`` adjust the speed to whatever suits your game best.

