- [ ] Section 18: User Roles and Permissions 3/3 | 54min
  - [ ] 82. User Roles and Permissions 20min
    - [ ] Default Roles
    - [ ] Custom Roles
    - [ ] Larger Web Sites Require a Team Effort
      - [ ] Too much content for one person to handle
      - [ ] Coworker that will help
      - [ ] Each person has an account
      - [ ] Users > Add New
        - [ ] Kitty-Doe, Remaining Time: 18:00-15:05
          - [ ] 15:40 Kitty-Doe is set with the Editor Role
      - [ ] Incognito Login 15:05
    - [ ] Access to all Post Types
    - [ ] 13:55 Limit access to all Post Types
      - [ ] 13:47 Limit Access to Event Posts - How do I give them access to (only) that ONE Post Type?
      - [ ] 13:28 We Can Create a New "Event Planner" Role...
        - [ ] ...and only grant the exact permissions that we want.
        - [ ] How do we create a new role?
        - [ ] 13:05 Role-Creation Plugin (Free) >> "Members by MemberPress"
        - [ ] **08:00/11:58 Let's create a new custom user role than only manage the Event Post Type**
          - Members
            - Roles
            - Create a brand-new role
            - Event Planner
            - Checkboxes
              - Posts, Pages
        - We don't see a tab for our Custom Post Types!
        - New CPTs are usually treated as Blog Posts
        - Edit the code where we registered the Event Post Type
          - mu-plugins/Custom-Post-Types/cpt-event.php
          - We want to tell the Event Post Type that it should not behave like a Blog Post when it comes to Permissions and Capabilities. Instead, it should require its own UNIQUE Permissions and Capabilities.
          
          ```php
          ...
          'capability_type' => 'event', // 'event' permissions, 'post' by default, see next line
          'map_meta_cap'    => true,    // These two lines add 'Events' to the Members Plugin
          ...
          ```
          
          - The "Events" Capability will now appear in the Capabilities Listing
          - Grant the Event Planner Role all of the Events Permissions
          - Change Kitty-Doe from an Editor to an Event Planner
          - Add some additional Events
          - Make sure that the Administrator Role can see the Events
          - Multiple Roles: Event Planner, Campus Manager
    - [ ] Redirect from Profile Page
    - [ ] Remove Dashboard
    - [ ] Remove Top Line?
  - [ ] 83. Open Registration 20min
    - Why are we Doing This?
      - Permissions
      - Security
      - CRUD user-specific content
      - 01:28 Open Registration
        - Admin Dashboard
        - Settings
        - Membership
        - Anyone can register
        - New User Default Role: Subscriber
  - [ ] 84. Open Registration (Part 2) 14min
