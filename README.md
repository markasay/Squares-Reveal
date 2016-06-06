# Squares-Reveal
First attempt at squares reveal type game


<div class="right_game_part">
<div id="board" class="game_board" style="height: auto;">

<style>
@media screen and (min-color-index: 0) and(-webkit-min-device-pixel-ratio: 0) { 

    @media {

        .game_board_img_container_list {
            -webkit-perspective: 500px;
            perspective: 500px;
        }
        .game_board_img_container_list .game_board_img_box {
            -webkit-transform-style: preserve-3d;
            transform-style: preserve-3d;
            -webkit-transform-origin: center center;
            transform-origin: center center;
            -webkit-transform: translateZ(-106px);
            -webkit-perspective: none !important;
            perspective: none !important;
        }
        .game_board_img_container_list .game_board_img_box_side {
            -webkit-transform-style: preserve-3d;
            transform-style: preserve-3d;
            -webkit-transform-origin: top left;
            transform-origin: top left;
        }
        .game_board_img_container_list .game_board_img_box_side.game_board_img_box_side_front {
            z-index: 2;
            background-color: #fff;
        }
        .game_board_img_container_list .game_board_img_box_side.game_board_img_box_side_revealed {
            z-index: 3;
        }
        .game_board_img_container_list.game_board_img_container_list_revealed .game_board_img_box_side.game_board_img_box_side_front {
            -webkit-animation: animate-safari-new1 1s ease-out;
            animation: animate-safari-new1 1s ease-out;
            -webkit-animation-fill-mode: forwards;
            animation-fill-mode: forwards;
        }
        .game_board_img_container_list.game_board_img_container_list_revealed .game_board_img_box_side.game_board_img_box_side_revealed {
            -webkit-animation: animate-safari-new2 1s ease-out;
            animation: animate-safari-new2 1s ease-out;
            -webkit-animation-fill-mode: forwards;
            animation-fill-mode: forwards;
        }
        .game_board_img_container_list.game_board_img_container_list_revealed.game_board_img_container_list_outdated .game_board_img_box_side.game_board_img_box_side_front {
            -webkit-animation: none 0 ease 0 1 normal none running;
            animation: none 0 ease 0 1 normal none running;
            display: none;
        }
        .game_board_img_container_list.game_board_img_container_list_revealed.game_board_img_container_list_outdated .game_board_img_box_side.game_board_img_box_side_revealed {
            -webkit-animation: none 0 ease 0 1 normal none running;
            animation: none 0 ease 0 1 normal none running;
        }
        @-webkit-keyframes animate-safari-new1 {
            0% {
                -webkit-transform: rotateY(0deg) translateZ(0);
            }
            100% {
                -webkit-transform: rotateY(-90deg) translateZ(0);
            }
        }
        @-webkit-keyframes animate-safari-new2 {
            0% {
                -webkit-transform: rotateY(90deg) translateZ(0);
            }
            100% {
                -webkit-transform: rotateY(0deg) translateZ(0);
            }
        }
    }
}

_::-moz-svg-foreign-content, :root .game_board_img_container_list {
    -webkit-perspective: 500px;
    perspective: 500px;
}
_::-moz-svg-foreign-content, :root .game_board_img_container_list .game_board_img_box {
    -webkit-transform-style: preserve-3d;
    transform-style: preserve-3d;
    -webkit-transform-origin: center center;
    transform-origin: center center;
    -webkit-transform: translateZ(-106px);
    -webkit-perspective: none;
    perspective: none;
}
_::-moz-svg-foreign-content, :root .game_board_img_container_list .game_board_img_box_side {
    -webkit-transform-style: preserve-3d;
    transform-style: preserve-3d;
    -webkit-transform-origin: top left;
    transform-origin: top left;
}
_::-moz-svg-foreign-content, :root .game_board_img_container_list .game_board_img_box_side.game_board_img_box_side_front {
    z-index: 2;
    background-color: #fff;
}
_::-moz-svg-foreign-content, :root .game_board_img_container_list .game_board_img_box_side.game_board_img_box_side_revealed {
    z-index: 3;
}
_::-moz-svg-foreign-content, :root .game_board_img_container_list.game_board_img_container_list_revealed .game_board_img_box_side.game_board_img_box_side_front {
    -webkit-animation: animate-safari1 1s ease-out;
    animation: animate-safari1 1s ease-out;
    -webkit-animation-fill-mode: forwards;
    animation-fill-mode: forwards;
}
_::-moz-svg-foreign-content, :root .game_board_img_container_list.game_board_img_container_list_revealed .game_board_img_box_side.game_board_img_box_side_revealed {
    -webkit-animation: animate-safari2 1s ease-out;
    animation: animate-safari2 1s ease-out;
    -webkit-animation-fill-mode: forwards;
    animation-fill-mode: forwards;
}
_::-moz-svg-foreign-content, :root .game_board_img_container_list.game_board_img_container_list_revealed.game_board_img_container_list_outdated .game_board_img_box_side.game_board_img_box_side_front {
    -webkit-animation: none 0 ease 0 1 normal none running;
    animation: none 0 ease 0 1 normal none running;
    display: none;
}
_::-moz-svg-foreign-content, :root .game_board_img_container_list.game_board_img_container_list_revealed.game_board_img_container_list_outdated .game_board_img_box_side.game_board_img_box_side_revealed {
    -webkit-animation: none 0 ease 0 1 normal none running;
    animation: none 0 ease 0 1 normal none running;
}

@-webkit-keyframes animate-safari1 {
    0% {
        -webkit-transform: rotateY(0deg) translateZ(0);
    }
    100% {
        -webkit-transform: rotateY(-90deg) translateZ(0);
    }
}
@-webkit-keyframes animate-safari2 {
    0% {
        -webkit-transform: rotateY(90deg) translateZ(0);
    }
    100% {
        -webkit-transform: rotateY(0deg) translateZ(0);
    }
}
</style>
    <!-- <div id="board_header_message" class="board_header_message_visible">
        HOVER OVER A SQUARE AND SEE A FUN FACT!
    </div>
    <div id="board_header_intro_message" class="board_header_intro_message board_header_intro_message_hidden">
        PLEASE VIEW INSTRUCTIONS BEFORE PLAYING
    </div> -->
    <ul class="game_board_img_container">
        <li id="game_board_li_item_p0" class="game_board_img_container_list game_board_img_container_list_kiwi game_board_img_container_list_revealed game_board_img_container_list_outdated">
            <div class="game_board_img_box">
                <div class="game_board_img_box_side game_board_img_box_side_front" style="transform-origin: 50% 50% -36.5px;"><!--   --></div>
                <div class="game_board_img_box_side game_board_img_box_side_revealed " style="transform-origin: 50% 50% -36.5px;">
                    <img id="game_board_img_item_p0" class="game_board_img_container_img" data_click_event_bind="" src="/vitality/styles/css/reskin/squares/images/vs/fruits/kiwi_square_tr.png" style="touch-action: pan-y; -webkit-user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);">
                </div>
            </div>
        </li>
        <li id="game_board_li_item_p1" class="game_board_img_container_list game_board_img_container_list_orange game_board_img_container_list_revealed game_board_img_container_list_outdated">
            <div class="game_board_img_box">
                <div class="game_board_img_box_side game_board_img_box_side_front" style="transform-origin: 50% 50% -36.5px;"><!--   --></div>
                <div class="game_board_img_box_side game_board_img_box_side_revealed " style="transform-origin: 50% 50% -36.5px;">
                    <img id="game_board_img_item_p1" class="game_board_img_container_img" data_click_event_bind="" src="/vitality/styles/css/reskin/squares/images/vs/fruits/orange_square_tr.png" style="touch-action: pan-y; -webkit-user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);">
                </div>
            </div>
        </li>
        <li id="game_board_li_item_p2" class="game_board_img_container_list game_board_img_container_list_apple game_board_img_container_list_revealed game_board_img_container_list_outdated">
            <div class="game_board_img_box">
                <div class="game_board_img_box_side game_board_img_box_side_front" style="transform-origin: 50% 50% -36.5px;"><!--   --></div>
                <div class="game_board_img_box_side game_board_img_box_side_revealed " style="transform-origin: 50% 50% -36.5px;">
                    <img id="game_board_img_item_p2" class="game_board_img_container_img" data_click_event_bind="" src="/vitality/styles/css/reskin/squares/images/vs/fruits/apple_square_tr.png" style="touch-action: pan-y; -webkit-user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);">
                </div>
            </div>
        </li>
        <li id="game_board_li_item_p3" class="game_board_img_container_list game_board_img_container_list_icecream game_board_img_container_list_revealed game_board_img_container_list_outdated">
            <div class="game_board_img_box">
                <div class="game_board_img_box_side game_board_img_box_side_front" style="transform-origin: 50% 50% -36.5px;"><!--   --></div>
                <div class="game_board_img_box_side game_board_img_box_side_revealed " style="transform-origin: 50% 50% -36.5px;">
                    <img id="game_board_img_item_p3" class="game_board_img_container_img" data_click_event_bind="" src="/vitality/styles/css/reskin/squares/images/vs/fruits/icecream_square_tr.png" style="touch-action: pan-y; -webkit-user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);">
                </div>
            </div>
        </li>
        <li id="game_board_li_item_p4" class="game_board_img_container_list game_board_img_container_list_strawberry game_board_img_container_list_revealed game_board_img_container_list_outdated">
            <div class="game_board_img_box">
                <div class="game_board_img_box_side game_board_img_box_side_front" style="transform-origin: 50% 50% -36.5px;"><!--   --></div>
                <div class="game_board_img_box_side game_board_img_box_side_revealed " style="transform-origin: 50% 50% -36.5px;">
                    <img id="game_board_img_item_p4" class="game_board_img_container_img" data_click_event_bind="" src="/vitality/styles/css/reskin/squares/images/vs/fruits/strawberry_square_tr.png" style="touch-action: pan-y; -webkit-user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);">
                </div>
            </div>
        </li>
        <li id="game_board_li_item_p5" class="game_board_img_container_list game_board_img_container_list_soda game_board_img_container_list_revealed game_board_img_container_list_outdated">
            <div class="game_board_img_box">
                <div class="game_board_img_box_side game_board_img_box_side_front" style="transform-origin: 50% 50% -36.5px;"><!--   --></div>
                <div class="game_board_img_box_side game_board_img_box_side_revealed " style="transform-origin: 50% 50% -36.5px;">
                    <img id="game_board_img_item_p5" class="game_board_img_container_img" data_click_event_bind="" src="/vitality/styles/css/reskin/squares/images/vs/fruits/soda_square_tr.png" style="touch-action: pan-y; -webkit-user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);">
                </div>
            </div>
        </li>
        <li id="game_board_li_item_p6" class="game_board_img_container_list game_board_img_container_list_banana game_board_img_container_list_revealed game_board_img_container_list_outdated">
            <div class="game_board_img_box">
                <div class="game_board_img_box_side game_board_img_box_side_front" style="transform-origin: 50% 50% -36.5px;"><!--   --></div>
                <div class="game_board_img_box_side game_board_img_box_side_revealed game_board_img_box_side_revealed_automatically" style="transform-origin: 50% 50% -36.5px;">
                    <img id="game_board_img_item_p6" class="game_board_img_container_img_dark" data_click_event_bind="" src="/vitality/styles/css/reskin/squares/images/vs/fruits/banana_square_tr.png" style="touch-action: pan-y; -webkit-user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);">
                </div>
            </div>
        </li>
        <li id="game_board_li_item_p7" class="game_board_img_container_list game_board_img_container_list_hotdog game_board_img_container_list_revealed game_board_img_container_list_outdated">
            <div class="game_board_img_box">
                <div class="game_board_img_box_side game_board_img_box_side_front" style="transform-origin: 50% 50% -36.5px;"><!--   --></div>
                <div class="game_board_img_box_side game_board_img_box_side_revealed game_board_img_box_side_revealed_automatically" style="transform-origin: 50% 50% -36.5px;">
                    <img id="game_board_img_item_p7" class="game_board_img_container_img_dark" data_click_event_bind="" src="/vitality/styles/css/reskin/squares/images/vs/fruits/hotdog_square_tr.png" style="touch-action: pan-y; -webkit-user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);">
                </div>
            </div>
        </li>
        <li id="game_board_li_item_p8" class="game_board_img_container_list game_board_img_container_list_pizza game_board_img_container_list_revealed game_board_img_container_list_outdated">
            <div class="game_board_img_box">
                <div class="game_board_img_box_side game_board_img_box_side_front" style="transform-origin: 50% 50% -36.5px;"><!--   --></div>
                <div class="game_board_img_box_side game_board_img_box_side_revealed game_board_img_box_side_revealed_automatically" style="transform-origin: 50% 50% -36.5px;">
                    <img id="game_board_img_item_p8" class="game_board_img_container_img_dark" data_click_event_bind="" src="/vitality/styles/css/reskin/squares/images/vs/fruits/pizza_square_tr.png" style="touch-action: pan-y; -webkit-user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);">
                </div>
            </div>
        </li>
        <li id="game_board_li_item_p9" class="game_board_img_container_list game_board_img_container_list_grape game_board_img_container_list_revealed game_board_img_container_list_outdated">
            <div class="game_board_img_box">
                <div class="game_board_img_box_side game_board_img_box_side_front" style="transform-origin: 50% 50% -36.5px;"><!--   --></div>
                <div class="game_board_img_box_side game_board_img_box_side_revealed game_board_img_box_side_revealed_automatically" style="transform-origin: 50% 50% -36.5px;">
                    <img id="game_board_img_item_p9" class="game_board_img_container_img_dark" data_click_event_bind="" src="/vitality/styles/css/reskin/squares/images/vs/fruits/grape_square_tr.png" style="touch-action: pan-y; -webkit-user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);">
                </div>
            </div>
        </li>
        <li id="game_board_li_item_p10" class="game_board_img_container_list game_board_img_container_list_donut game_board_img_container_list_revealed game_board_img_container_list_outdated">
            <div class="game_board_img_box">
                <div class="game_board_img_box_side game_board_img_box_side_front" style="transform-origin: 50% 50% -36.5px;"><!--   --></div>
                <div class="game_board_img_box_side game_board_img_box_side_revealed game_board_img_box_side_revealed_automatically" style="transform-origin: 50% 50% -36.5px;">
                    <img id="game_board_img_item_p10" class="game_board_img_container_img_dark" data_click_event_bind="" src="/vitality/styles/css/reskin/squares/images/vs/fruits/donut_square_tr.png" style="touch-action: pan-y; -webkit-user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);">
                </div>
            </div>
        </li>
        <li id="game_board_li_item_p11" class="game_board_img_container_list game_board_img_container_list_hamburger game_board_img_container_list_revealed game_board_img_container_list_outdated">
            <div class="game_board_img_box">
                <div class="game_board_img_box_side game_board_img_box_side_front" style="transform-origin: 50% 50% -36.5px;"><!--   --></div>
                <div class="game_board_img_box_side game_board_img_box_side_revealed game_board_img_box_side_revealed_automatically" style="transform-origin: 50% 50% -36.5px;">
                    <img id="game_board_img_item_p11" class="game_board_img_container_img_dark" data_click_event_bind="" src="/vitality/styles/css/reskin/squares/images/vs/fruits/hamburger_square_tr.png" style="touch-action: pan-y; -webkit-user-select: none; -webkit-user-drag: none; -webkit-tap-highlight-color: rgba(0, 0, 0, 0);">
                </div>
            </div>
        </li>
    </ul>
</div>


<script>
    $(document).ready(function() {
            prepareItemsHoverEvents('/vitality');
    });

</script>					</div>
