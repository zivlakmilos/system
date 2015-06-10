import XMonad
import XMonad.Layout.Spacing

defaultLayouts = tiled ||| Mirror tiled ||| Full
    where
        -- default tiling algorithm partitions the screen into two panes
        tiled = spacing 5 $ Tall nmaster delta ratio

        -- The default number of windows in the master pane
        nmaster = 1

        -- Default proportion of screen occupied by master pane
        ratio = 2/3

        -- Percent of screen to increment by when resizing panes
        delta = 5/100

--nonborderLayout = noBorders $ Full
--myLayout = onWorkspace "8:chat" nonborderLayout $ defaultLayouts
myLayout = defaultLayouts

myWorkspaces = ["1:main", "2:code", "3:web", "5:media", "6:graphics", "7", "8:chat"]

myManageHook = composeAll
    [ className =? "firefox" --> doShift "3:web"
    ]

main = do
    xmonad $ defaultConfig
        {workspaces = myWorkspaces
        ,layoutHook = myLayout
        ,manageHook = myManageHook
        }
