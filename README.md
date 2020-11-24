<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" itemscope
      itemtype="http://qrco.de/bbq8Xp?trackSharing=1">
<head>
    <link rel="stylesheet" type="text/css" href="/css/build/pages/dsocial/template_normal.min.css?v=1.226" />
<script type="text/javascript">
/*<![CDATA[*/
YII_CSRF_TOKEN='87d6a241cddc265d13364faedfcd666c721765dc';
/*]]>*/
</script>
<title>Social Media Page</title>
    <meta charset="utf-8"/>
    <meta http-equiv="X-UA-Compatible" content="IE=edge"/>
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no"/>
    <meta name="robots" content="noindex, nofollow"/>
    <meta name="apple-mobile-web-app-capable" content="yes"/>
    <link rel="shortcut icon" href="/img/favicon/favicon.ico" type="image/x-icon"/>
        <link href="https://fonts.googleapis.com/css?family=Roboto" rel="stylesheet">

    <!--Facebook meta-->
    <meta property="og:url"
          content="http://qrco.de/bbq8Xp?trackSharing=1"/>
    <meta property="og:title" content="Connect with us on social media"/>
    <meta property="og:description" content="Follow us and get updates delivered to your favorite social media channel."/>
    <meta property="og:image" content="http:"/>
    <meta property="og:image:width" content="200"/>
    <meta property="og:image:height" content="200"/>

    <!-- Twitter Card data -->
    <meta name="twitter:card" content="summary">
    <meta name="twitter:url" content="http://qrco.de/bbq8Xp?trackSharing=1">
    <meta name="twitter:title" content="Connect with us on social media">
    <meta name="twitter:description" content="Follow us and get updates delivered to your favorite social media channel.">
    <meta name="twitter:image" content="http:">
    <meta name="twitter:image:width" content="200">
    <meta name="twitter:image:height" content="200">

    <!-- Schema.org markup for Google+ -->
    <meta itemprop="name" content="Connect with us on social media">
    <meta itemprop="description" content="Follow us and get updates delivered to your favorite social media channel.">
    <meta itemprop="image" content="http:">

</head>
<body ng-app="app" id="dsocial-body" ng-controller="ComplexController"
      class="{{isColorLight(view.code.color1) ? 'darkTheme' : 'whiteTheme'}}">

<div class="loading-welcome active welcome-screen"
     ng-style="{'background-color': view.code.welcome_extra.background || view.welcome_extra.background}"
        style="background-color: #ffffff">
    <div class="progress">
        <div class="loading-bar indeterminate" ng-style="{'background-color': view.code.color1 || view.color1}"></div>
    </div>
    <div class="helper"></div>
    <img id="welcomeImg" imageonload ng-src="{{view.welcome_screen || '//s3.eu-central-1.amazonaws.com/qrcgappcdn/social-media-solution/welcome.png'}}"
         ng-style="{
            'max-width': view.code.welcome_extra.zoom *2 || view.welcome_extra.zoom *2 + 'px',
            'max-height': view.code.welcome_extra.zoom *2 || view.welcome_extra.zoom *2 + 'px',
            'animation-iteration-count' :  view.showPreview == 'infinite' ? 'infinite' : '',
            'animation-direction' :  view.showPreview == 'infinite' ? 'alternate' : ''
            }">
</div>

<div class="vcard-template style2" id="rootElement">
    <div ng-if="!view.code.avatar && !view.code.customHeaderImage">
        <div class="solid-bgd" ng-style="setSolidBgd()">
        </div>
    </div>
    <div ng-if="view.code.avatar || view.code.customHeaderImage">
        <div class="blur-bgd hidden-sm hidden-xs"
             ng-style="{'background': view.code.avatar.length > 0 || view.code.customHeaderImage !=undefined ? 'url(' + (view.code.avatar.length > 0 ? view.code.avatar : view.code.customHeaderImage.url) +')' : 'none'}"
             ng-class="{'blur-no-avatar':!view.code.avatar && !view.code.customHeaderImage}">
        </div>
    </div>
    <div class="bgd-shadow"></div>
    <!--    <pre>avatar_extra: {{view.code.avatar_extra | json}}</pre>-->
    <!--    <pre>welcome_extra: {{view.code.welcome_extra | json}}</pre>-->
    <div class="page-home page">
        <div class="vcard-header">
            <div class="vcard-header-wrapper">
                <div class="vcard-top-info avatar-container" ng-style="setAvatarExtra()">
                </div>
                <div class="event-section-title"
                     ng-class="{'shadow-2': !view.code.avatar || !view.code.customHeaderImage}"
                     ng-style="getBackgroundColor();">
                    <div class="event-content-container">
                        <div class="event-title dynamicTextColor">{{view.code.title}}</div>
                        <div class="event-teaser mt-10 dynamicTextColor"
                             ng-show="view.code.teaser && (view.code.avatar || view.code.customHeaderImage)">
                            {{view.code.teaser}}
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="event-body">
            <div class="vcard-body-wrapper">
                <div class="vcard-body">
                    <div id="devent-details">
    <div class="channel-container event-teaser"
         ng-if="view.code.avatar == '' && !view.code.customHeaderImage && view.code.teaser">
        <span class="table-cell-middle">{{view.code.teaser}}</span>
    </div>
    <a ng-href="{{getChannelLink(channel)}}"
       target="{{!loadDemo ? '_blank' : '_self'}}"
       class="channel-container"
       id="channel-item-{{channel.name}}"
       ng-click="loadDemo ? callAction($event,'channelAction') : ''"
       ng-repeat="channel in view.code.channels track by $index">
        <div class="table-cell-middle1 pl-55 pos-relative">
            <div class="channel-bgd-{{channel.name | toIconName}}"
                 ng-style="{top: channel.label ? 'calc(50% - 20px)' : 'calc(50% - 15px)'}">
                <i ng-if="channel.name != 'Snapchat'"
                   class="icon-social-{{channel.name | toIconName}}"></i>
                <svg ng-if="channel.name == 'Snapchat'" version="1.1" id="Ebene_1"
                     xmlns="http://www.w3.org/2000/svg"
                     xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="40px" height="40px"
                     viewBox="0 0 40 40" enable-background="new 0 0 40 40" xml:space="preserve">
<g>
    <path stroke-linejoin="round" stroke="black" stroke-width="1" d="M29.8,25.6c-2.9-0.5-4.2-3.5-4.2-3.6c0,0,0,0,0,0c-0.2-0.4-0.2-0.7-0.1-0.9c0.2-0.5,0.8-0.7,1.3-0.8c0.1,0,0.2-0.1,0.3-0.1
		c0.7-0.3,0.9-0.6,0.9-0.8c0-0.2-0.2-0.4-0.5-0.5l0,0c-0.1,0-0.2-0.1-0.3-0.1c-0.1,0-0.2,0-0.3,0.1c-0.4,0.2-0.7,0.3-1,0.3h0
		c-0.4,0-0.5-0.2-0.6-0.2c0-0.2,0-0.4,0-0.6l0-0.1c0.1-1.4,0.2-3.1-0.2-4.1c-1.3-2.9-4-3.2-4.9-3.2l0,0c0,0-0.3,0-0.4,0
		c-0.8,0-3.6,0.2-4.9,3.2c-0.4,1-0.3,2.7-0.2,4.1c0,0.2,0,0.4,0,0.6c0,0-0.2,0.2-0.6,0.2c-0.3,0-0.6-0.1-1-0.3c-0.1,0-0.1,0-0.2,0
		c-0.3,0-0.7,0.2-0.8,0.5c0,0.2,0,0.5,0.9,0.9c0.1,0,0.2,0.1,0.3,0.1c0.4,0.1,1.1,0.3,1.3,0.8c0.1,0.3,0.1,0.6-0.1,0.9c0,0,0,0,0,0
		c-0.1,0.1-1.3,3.1-4.2,3.6c-0.1,0-0.2,0.1-0.2,0.2c0,0,0,0.1,0,0.1c0.1,0.3,0.7,0.7,2.5,1c0.2,0,0.2,0.3,0.3,0.7
		c0,0.2,0.1,0.3,0.1,0.5c0.1,0.2,0.2,0.2,0.3,0.2c0.1,0,0.3,0,0.4-0.1c0.3-0.1,0.7-0.1,1.1-0.1c0.3,0,0.5,0,0.8,0.1
		c0.6,0.1,1,0.4,1.6,0.8c0.7,0.5,1.5,1.1,2.7,1.1c0,0,0.1,0,0.1,0h0c0.1,0,0.1,0,0.2,0c1.2,0,1.9-0.5,2.7-1.1c0.5-0.4,1-0.7,1.5-0.8
		c0.3,0,0.6-0.1,0.8-0.1c0.5,0,0.8,0.1,1.1,0.1c0.2,0,0.3,0.1,0.4,0.1h0c0.1,0,0.2-0.1,0.3-0.2c0-0.2,0.1-0.3,0.1-0.5
		c0.1-0.4,0.2-0.6,0.3-0.7c1.9-0.3,2.4-0.7,2.5-1c0,0,0-0.1,0-0.1C30,25.7,29.9,25.6,29.8,25.6z"
          fill="white"></path>
</g>
</svg>
            </div>
            <div class="channel-prop-container"
                 ng-class="{'pull-left': channel.link && channel.label && channel.name == 'Website', 'pull-left mt-101 height-301': channel.link && !channel.label && channel.name == 'Website', 'pt-10': !channel.label}">

                <span ng-if="channel.name == 'Website'">
                    <span ng-if="channel.label">
                             <div class="channel-name" ng-class="{'mb-5': channel.label}">
                            {{channel.label}}
                            </div>
                            <div class="channel-label">
                                {{getChannelNameOrLink(channel)}}
                            </div>
                    </span>
                    <span ng-if="!channel.label">
                             <div class="channel-name" ng-class="{'mb-5': channel.label}">
                            {{getChannelNameOrLink(channel)}}
                            </div>
                            <div class="channel-label">
                                {{channel.label}}
                            </div>
                    </span>
                </span>
                <span ng-if="channel.name != 'Website'">
                    <div class="channel-name" ng-class="{'mb-5': channel.label}">
                    {{getChannelNameOrLink(channel)}}
                    </div>
                    <div class="channel-label">
                        {{channel.label}}
                    </div>
                </span>
            </div>
        </div>
    </a>
</div>
<div class="vcard-row follow-scroll share-container"
     ng-show="view.sharing">
    <div class="fabs" id="shareFab">
    <div class="fixed-blur-bgd">
        <div class="chat">
            <div class="fab-body">
                <div class="icon-fab-close"></div>
                <div class="fab-header"
                     ng-style="{color: isColorLight(view.code.color2) ? 'black' : view.code.color2}">Share page</div>
                <ul class="ssk-block ssk-md"
                    data-url="http://qrco.de/bbq8Xp?trackSharing=1"
                    data-text="">
                    <li>
                        <i class="icon-fab-share-facebook"></i>
                        <a href="" class="ssk ssk-text ssk-facebook">Facebook</a>
                    </li>
                    <li>
                        <i class="icon-fab-share-twitter"></i>
                        <a href="" class="ssk ssk-text ssk-twitter">Twitter</a>
                    </li>
                    <li>
                        <i class="icon-fab-share-googleplus"></i>
                        <a href="" class="ssk ssk-text ssk-google-plus">Google+</a>
                    </li>
                    <li>
                        <i class="iconFab icon-fab-share-whatsapp"></i>
                        <a href="whatsapp://send?text=http://qrco.de/bbq8Xp?trackSharing=1" class="ssk ssk-whatsapp">Whatsapp</a>
                    </li>
                    <li>
                        <i class="icon-fab-share-email"></i>
                        <a href="mailto:?body=http://qrco.de/bbq8Xp?trackSharing=1"
                           target="_blank">Email</a>
                    </li>
                    <li>
                        <i class="icon-fab-share-message"></i>
                        <input id="shortUrl" value="http://qrco.de/bbq8Xp" readonly>
                        <button id="copyButton">Copy</button>
                        <div class="ifCopySucceed" ng-show="ifCopySucceed">
                            Text copied to the clipboard.                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
    <a id="{{!loadDemo ? 'prime' : ''}}" class="fab"
       ng-style="{background: view.code.color2 || '#ea4b88'}"
       ng-click="!loadDemo ?  '' : callAction($event,'shareAction')">
        <span class="hidden-xs" ng-style="{'color': isColorLight(view.code.color2) ? 'black' : 'white'}">
            <i class="prime icon icon-fab-share"></i>
            Share this page        </span>
        <i class="prime icon icon-fab-share visible-xs"
           ng-style="{'color': isColorLight(view.code.color2) ? 'black' : 'white'}"></i>
    </a>
</div></div>


<div id="redirectTo">
    <div class="fixed-blur-bgd">
        <div class="dialog-container">
            <div class="fab-body">
                <div class="event-title">
                    Continue?                </div>
                <div class="dialog-body">
                    You will be directed to another website.                </div>
                <a class="event-slim-button ripplelink mt-10 pull-right" ng-style="{'color': isColorLight(view.color2) ? 'black' : view.color2}"
                   ng-click="dialogRedirectCallback(false)">
                    No                </a>
                <a class="event-slim-button ripplelink mt-10 pull-right" ng-style="{'color': isColorLight(view.color2) ? 'black' : view.color2}"
                   ng-click="dialogRedirectCallback(true)">
                    Yes                </a>
            </div>
        </div>
    </div>
</div>

<div id="gotIt">
    <div class="fixed-blur-bgd">
        <div class="dialog-container">
            <div class="fab-body">
                <div class="event-gotIt-button">
                </div>
                <div class="dialog-body pull-left">
                    {{gotItText}}
                </div>
                <a class="text-regular-blue mt-20" ng-click="closeDialog()">
                    Got it                </a>
            </div>
        </div>
    </div>
</div>

<div id="eventOver">
    <div class="fixed-blur-bgd">
        <div class="dialog-container">
            <div class="fab-body">
                <div class="event-title">
                    Event has passed                </div>
                <div class="dialog-body">
                    Registration and ticket purchases have closed for this event.                </div>
                <a class="event-slim-button ripplelink mt-10 pull-right" ng-style="{'color': isColorLight(view.color2) ? 'black' : view.color2}"
                   ng-click="dialogRedirectCallback(true)">
                    Close                </a>
            </div>
        </div>
    </div>
</div>                </div>
            </div>
        </div>
    </div>
</div>
<script type="text/javascript" src="/public/lib/jquery/dist/jquery.min.js?v=1.226"></script>
<script type="text/javascript" src="/js/build/angular.rendering.min.js?v=1.226"></script>
<script type="text/javascript">
/*<![CDATA[*/


    /**
     * Angular connection
     */
    app.loadBasePreviewController();


    /**
     * Replace a point with a space character
     */
    app.filter('point2space', function () {
        return function (input) {
            if (input) {
                return input.replace(/\./g, ' ');
            }
        }
    });

    /**
     * Return date in number format '1490189463876'
     *
     * @param input - date
     * */
    app.filter('toDay', function () {
        return function (input) {
            if (input) {
                var result = new Date(input).getTime();
                return result || '';
            } else
                return '';
        };
    });

    /**
     * Return value with '-' instead of spaces
     *
     * @param input - string
     * */
    app.filter('dashEncode', function () {
        return function (input) {
            if (input) {
                return input.replace(/ /g, "-");
            } else
                return ' ';
        };
    });

    /**
     * Return escape value of param
     *
     * @param input - string
     * */
    app.filter('escape', function () {
        return function (input) {
            if (input) {
                return escape(input);
            } else
                return ' ';
        };
    });

    /**
     * Return icon name based on the channel name
     * */
    app.filter('toIconName', function () {
        return function (input) {
            if (input) {
                return input.replace(/\s+/g, '').toLowerCase();
            } else
                return ' ';
        };
    });

    /**
     * Return link with the correct prefix
     * */
    app.filter('prefixChannel', ['$filter', function ($filter) {
        return function (input, name) {
            if (input) {
                switch (name) {
                    case ('Twitter'):
                        return $filter('prefixURL')('www.twitter.com/' + input);
                        break;
                    case ('Instagram'):
                        return $filter('prefixURL')('www.instagram.com/' + input);
                        break;
                    case ('Snapchat'):
                        return $filter('prefixURL')('www.snapchat.com/add/' + input);
                        break;
                    case ('WeChat'):
                        return 'weixin://dl/chat?' + input;
                        break;
                    case ('Skype'):
                        return 'skype:' + input + '?add';
                        break;
                    case ('Line'):
                        return $filter('prefixURL')('http://line.naver.jp/ti/p/@' + input);
                        break;
                    default:
                        return $filter('prefixURL')(input);
                        break;
                }
            } else
                return ' ';
        };
    }]);

    /**
     * Return domain of input
     * */
    app.filter('domain', function () {
        return function (input) {
            if (input.indexOf('://') >= 0) {
                return input.split('/')[2]
            }
            return input.split('/')[0]
        };
    });

    /**
     * The QR service for the app.
     * */
    app.service('qr', function () {
        /**
         * Scroll page from buttom to top
         * */
        this.scrollFromBottomtoTop = function (loadDemo) {
            setTimeout(function () {
                if (loadDemo == true) {
                    $("html, body").animate({
                        scrollTop: $('.channel-container:last-child').offset().top
                    }, 0)
                    ;$("html, body").animate({
                        scrollTop: 0
                    }, 1000);
                }
            }, 0)
        }
    });

    /**
     * Directive
     *
     * When image is loaded fadeout welcome screen
     * */
    app.directive('imageonload', ['qr', function (qr) {
        return {
            restrict: 'A',
            link: function (scope, element, attrs) {
                element.bind('load', function () {
                    $("#welcomeImg").fadeIn(1000);
                    window.setTimeout(function () {
                        $(".loading-welcome.welcome-screen").fadeOut();
                        scope.welcomeScreenScrollWindow++;
                        if (scope.welcomeScreenScrollWindow == 1) {
                            qr.scrollFromBottomtoTop(scope.loadDemo)
                        }
                    }, 2000);
                });
                element.bind('error', function () {
                });
            }
        };
    }]);
    //Override the base preview controller
    app.controller('ComplexController', function ($scope, $controller, $sce, $rootScope, $filter, previewService, $window) {

            $scope.welcomeScreenScrollWindow = 0;
            /**
             * Get channel name from channel item
             *
             * @param channel
             * */
            $scope.getChannelLink = function (channel) {
                if (!$scope.loadDemo) {
                    return $filter('prefixChannel')(channel.link, channel.name);
                }
                return '#channel-item-' + channel.name;
            };

            /**
             * Get channel name or link to the channel based on channel info
             *
             * @param channel
             * */
            $scope.getChannelNameOrLink = function (channel) {
                if (channel.name == 'Website')
                    if (channel.link) {
                        return $scope.loadDemo ? channel.link : $filter('domain')(channel.link);
                    } else {
                        return channel.name;
                    } else {
                    return channel.name;
                }
            };

            /**
             * Set solid background for the header based on the title section height
             * */
            $scope.setSolidBgd = function () {
                if ($scope.view.code) {
                    var titleSectionHeight = 142;
                    setTimeout(function () {
                        if ($scope.view.code.teaser) {
                            titleSectionHeight = $('.event-content-container').parent().outerHeight() + 60 + 128
                        }
                        else
                            titleSectionHeight = $('.event-content-container').parent().outerHeight() + 60;
                        $('.solid-bgd').css({
                            'background-color': $scope.view.code.color1 ? $scope.view.code.color1 : '#447fb6',
                            'height': !$scope.view.code.avatar ? titleSectionHeight + 'px' : '420px'
                        })
                    }, 0);
                }
            };

            /**
             * Open the dialog popup
             * Event is for getting the current target element
             * Target:
             *      - shareAction: Button with got it information
             *      - channelAction: Button with got it information
             *
             * @param event - string
             * @param target - string
             * */
            $scope.callAction = function (event, target) {
                switch (target) {
                    case 'shareAction':
                        if ($scope.loadDemo) {
                            $scope.gotItText = 'Your contacts can click this button to share your page.';
                            $scope.toggleDialog('gotIt', $(event.currentTarget));
                        }
                        break;
                    case 'channelAction':
                        if ($scope.loadDemo) {
                            $scope.gotItText = 'By tapping here, users are navigated to the linked social media profile or website.';
                            $scope.toggleDialog('gotIt', $(event.currentTarget));
                        }
                        break;
                }
            };


            /**
             * Toggle dialog
             *
             * @param id - string
             * @param element - current target
             * */
            $scope.toggleDialog = function (id, element) {
                if (element) {
                    var elem = element.context.outerHTML;
                    $('#' + id + ' .dialog-container .event-gotIt-button').html(elem);
                }
                $($('#' + id).parent()).toggleClass('fabOnTop');
                $('#' + id + ' .dialog-container').toggleClass('is-visible');
                $('#prime.fab').toggleClass('disabledClick');
                $('#' + id + ' .fixed-blur-bgd').toggle();
            };

            /**
             * Callback of the dialog yes/no buttons
             * Can close the dialog or it can redirect to a url and close the dialog
             * If the url is not defined it will use the targetUrl from the callAction button
             *
             * @param proceed - string
             * @param url - current target
             * */
            $scope.dialogRedirectCallback = function (proceed, url) {
                if (proceed) {
                    if (url) {
                        $window.open(url, '_blank');
                    } else {
                        if ($scope.view.code.callToAction.targetUrl.indexOf('http') < 0)
                            $window.open('//' + $scope.view.code.callToAction.targetUrl, '_blank');
                        else
                            $window.open($scope.view.code.callToAction.targetUrl, '_blank');
                    }
                    $scope.closeDialog();
                } else {
                    $scope.closeDialog();
                }
            };

            /**
             * Close dialog
             *
             * */
            $scope.closeDialog = function () {
                $('.dialog-container').removeClass('is-visible');
                $('#prime.fab').toggleClass('disabledClick');
                $('.event-gotIt-button').html('');
                $('.fixed-blur-bgd').hide();
            };


            /**
             * Set position of the fab Button
             *If we have only one fab you have to use bottom 5px!!! else use 75px as default
             * @param buttonName - string
             * */
            $scope.setPosition = function (buttonName) {
                if ($(window).innerWidth() < 667) {
                    var bottom = '5px',
                        right = '17px';
                    if (buttonName == 'calendar')
                        bottom = '5px';
                    if ($(window).innerWidth() < 321)
                        right = '-85px';
                    return {
                        'position': 'fixed',
                        'bottom': bottom,
                        'right': right,
                        'width': '80px'
                    }
                }
                return '';
            };

            //Inherrit from basePreviewController
            angular.extend(this, $controller('BasePreviewController', {$scope: $scope}));

            $scope.loadDemo = parent && typeof parent.ImHere === "function";

            //Get the json data form the file
            json_data = {"form":[{"section_design":{"fold":false}},{"section_basic_info":{"fold":false}},{"section_media_channels":{"fold":false}},{"section_welcome_screen":{"fold":false}},{"section_advance_options":{"fold":true}}],"code":{"title":"Connect with us on social media","teaser":"Follow us and get updates delivered to your favorite social media channel.","channels":[{"input_prefix_label":"URL","link":"www.your-website.com","label":"Visit us online","name":"Website"},{"input_prefix_label":"URL","label":"Become a fan","name":"Facebook","link":"facebook.com"},{"input_prefix_label":"@","link":"Axer","label":"Follow us","name":"Instagram"}],"color1":"#4caf50","color2":"#81c784","avatar":"","avatar_extra":{"zoom":100,"background":"#ffffff"},"welcome_extra":{"zoom":50,"background":"#ffffff"},"customHeaderImage":{"url":"data:image\/svg+xml;base64,PD94bWwgdmVyc2lvbj0iMS4wIiBlbmNvZGluZz0idXRmLTgiPz4KPCEtLSBHZW5lcmF0b3I6IEFkb2JlIElsbHVzdHJhdG9yIDIyLjAuMSwgU1ZHIEV4cG9ydCBQbHVnLUluIC4gU1ZHIFZlcnNpb246IDYuMDAgQnVpbGQgMCkgIC0tPgo8c3ZnIHZlcnNpb249IjEuMSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIiB4bWxuczp4bGluaz0iaHR0cDovL3d3dy53My5vcmcvMTk5OS94bGluayIgeD0iMHB4IiB5PSIwcHgiCgkgdmlld0JveD0iMCAwIDY0MCAzNjAiIGVuYWJsZS1iYWNrZ3JvdW5kPSJuZXcgMCAwIDY0MCAzNjAiIHhtbDpzcGFjZT0icHJlc2VydmUiPgo8ZyBpZD0iRWJlbmVfMSI+Cgk8Zz4KCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNzkuOSwxMDkuMmMtMC4yLDIuNC0xLjMsNC42LTMuMiw2LjFzLTQuMiwyLjMtNi42LDIuMUw1NC4zLDExNmMtMi40LTAuMi00LjYtMS4zLTYuMS0zLjIKCQkJYy0xLjUtMS44LTIuMy00LjItMi4xLTYuNmwxLjQtMTUuOWMwLjItMi40LDEuMy00LjYsMy4yLTYuMWMxLjYtMS40LDMuNy0yLjEsNS44LTIuMWMwLjMsMCwwLjUsMCwwLjgsMGwxNCwxLjIKCQkJYzAuMS0wLjcsMC40LTEuMywwLjYtMmwtMTQuNS0xLjNjLTIuOS0wLjMtNS44LDAuNi04LDIuNXMtMy42LDQuNS0zLjksNy41TDQ0LjEsMTA2Yy0wLjMsMi45LDAuNiw1LjgsMi41LDgKCQkJYzEuOSwyLjMsNC41LDMuNiw3LjUsMy45bDE1LjksMS40YzAuMywwLDAuNywwLDEsMGMyLjYsMCw1LjEtMC45LDcuMS0yLjZjMi4zLTEuOSwzLjYtNC41LDMuOS03LjVsMS40LTE1LjkKCQkJYy0wLjcsMC4zLTEuMywwLjQtMi4xLDAuNUw3OS45LDEwOS4yeiIvPgoJCTxwYXRoIG9wYWNpdHk9IjAuMiIgZmlsbD0iIzYxNjU2OCIgZD0iTTI5OC42LDMwMS4xbC01LjIsMC45Yy0wLjMsMC42LTAuNiwxLjEtMSwxLjdsLTYuMSw4LjdjLTAuNCwwLjYtMS4zLDAuNy0xLjksMC4zbC04LjctNi4xCgkJCWMtMC41LTAuNC0xLTAuOC0xLjUtMS4ybC02LjIsMS4xbDMsMTYuN2wzMC41LTUuNEwyOTguNiwzMDEuMXoiLz4KCQk8Zz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTE0Ny44LDEyMS4zYy0wLjIsMC0wLjMsMC0wLjUtMC4xbC0yLjEtMS4xYy03LjctMy45LTEyLjctNi41LTE0LTExLjNjLTAuNS0yLTAuMy00LDAuNy01LjgKCQkJCWMxLTEuNywyLjctMyw0LjYtMy41YzEuOS0wLjUsNC0wLjMsNS44LDAuNmMxLjEtMS43LDIuOC0yLjksNC43LTMuNGM0LjEtMS4xLDguMiwxLjMsOS4zLDUuNGMxLjMsNC44LTEuOCw5LjYtNi40LDE2LjhsLTEuMywyCgkJCQlDMTQ4LjUsMTIxLjEsMTQ4LjIsMTIxLjMsMTQ3LjgsMTIxLjN6IE0xMzguNywxMDEuMmMtMC41LDAtMSwwLjEtMS41LDAuMmMtMS41LDAuNC0yLjcsMS4zLTMuNCwyLjZzLTAuOSwyLjgtMC41LDQuMwoJCQkJYzEuMSw0LDUuOCw2LjQsMTMsMTAuMWwxLjMsMC43bDAuOC0xLjJjNC40LTYuOCw3LjMtMTEuMyw2LjItMTUuMmMtMC44LTMtMy44LTQuOC02LjktNGMtMS43LDAuNS0zLjIsMS43LTMuOSwzLjMKCQkJCWMtMC4xLDAuMy0wLjQsMC41LTAuNiwwLjVjLTAuMywwLjEtMC42LDAtMC44LTAuMUMxNDEuMiwxMDEuNiwxNDAsMTAxLjIsMTM4LjcsMTAxLjJ6Ii8+CgkJPC9nPgoJCTxnPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMTE4LjEsODguNWMtMC4zLDAtMC43LTAuMi0wLjgtMC41bC0wLjgtMS4zYy0zLjItNC45LTUuMi04LjEtNC4zLTExLjVjMC44LTIuOSwzLjctNC42LDYuNi0zLjgKCQkJCWMxLjMsMC4zLDIuNCwxLjEsMy4xLDIuMmMxLjItMC41LDIuNi0wLjYsMy44LTAuM2MxLjQsMC40LDIuNiwxLjMsMy4zLDIuNWMwLjcsMS4yLDAuOSwyLjcsMC41LDQuMWMtMC45LDMuMy00LjMsNS4xLTkuNSw3LjgKCQkJCWwtMS40LDAuN0MxMTguNCw4OC41LDExOC4zLDg4LjUsMTE4LjEsODguNXogTTExNy4zLDczLjJjLTEuNSwwLTIuOCwxLTMuMywyLjVjLTAuNywyLjUsMS4yLDUuNCw0LjEsOS45bDAuNCwwLjZsMC42LTAuMwoJCQkJYzQuNy0yLjQsNy44LTQsOC41LTYuNWMwLjItMC45LDAuMS0xLjgtMC4zLTIuNnMtMS4yLTEuMy0yLjEtMS42Yy0xLTAuMy0yLjItMC4xLTMuMSwwLjVjLTAuMiwwLjItMC41LDAuMi0wLjgsMC4xCgkJCQljLTAuMy0wLjEtMC41LTAuMy0wLjYtMC41Yy0wLjUtMS0xLjQtMS43LTIuNC0yQzExNy45LDczLjMsMTE3LjYsNzMuMiwxMTcuMyw3My4yeiIvPgoJCTwvZz4KCQk8ZyBvcGFjaXR5PSIwLjIiPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMTc2LjgsMTc3djUuM2gxNS4ydjEyLjdoLTE1LjJWMjA4aC0xNi41di00My4zaDMzLjlWMTc3SDE3Ni44eiIvPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMjM2LjYsMTkxYzAsMTEuMy05LjQsMTcuOC0yMC40LDE3LjhjLTExLjEsMC0yMC41LTYuNS0yMC41LTE3LjhzOS41LTE3LjgsMjAuNS0xNy44CgkJCQlDMjI3LjIsMTczLjMsMjM2LjYsMTc5LjgsMjM2LjYsMTkxeiBNMjIwLjksMTkxYzAtMy4yLTEuOS02LTQuOC02cy00LjgsMi44LTQuOCw2YzAsMy4yLDEuOSw2LDQuOCw2UzIyMC45LDE5NC4yLDIyMC45LDE5MXoiLz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTI0MC44LDE2MC43aDE2LjNWMjA4aC0xNi4zVjE2MC43eiIvPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMjYzLjEsMTYwLjdoMTYuM1YyMDhoLTE2LjNWMTYwLjd6Ii8+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0zMjQuNSwxOTFjMCwxMS4zLTkuNCwxNy44LTIwLjQsMTcuOGMtMTEuMSwwLTIwLjUtNi41LTIwLjUtMTcuOHM5LjUtMTcuOCwyMC41LTE3LjgKCQkJCUMzMTUuMSwxNzMuMywzMjQuNSwxNzkuOCwzMjQuNSwxOTF6IE0zMDguOCwxOTFjMC0zLjItMS45LTYtNC44LTZzLTQuOCwyLjgtNC44LDZjMCwzLjIsMS45LDYsNC44LDZTMzA4LjgsMTk0LjIsMzA4LjgsMTkxeiIvPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMzg1LjQsMTc0LjFMMzc1LjIsMjA4aC0xNS44bC00LjUtMTUuNGwtNC43LDE1LjRoLTE1LjdsLTEwLjItMzMuOWgxNi42bDMuMywxOC41bDQuOC0xOC41aDExLjYKCQkJCWw1LjEsMTguNWwzLjUtMTguNUgzODUuNHoiLz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTQ0NS44LDE2NC43djI2LjJjMCwxMi4zLTcuOCwxNy45LTIwLjksMTcuOXMtMjAuOS01LjYtMjAuOS0xNy45di0yNi4yaDE2Ljd2MjZjMCwzLjEsMC42LDUuNCw0LjIsNS40CgkJCQljMy42LDAsNC4yLTIuNCw0LjItNS40di0yNkg0NDUuOHoiLz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTQ4MS43LDE5N2MwLDgtNi40LDExLjgtMTYuNCwxMS44Yy01LjYsMC0xMS0xLjUtMTUuNC0zLjlsMS41LTkuN2MyLjksMS45LDcuMiwzLjUsMTEuNSwzLjUKCQkJCWMxLjcsMCwyLjctMC40LDIuNy0xLjNjMC0yLjEtMTQuNiwwLTE0LjYtMTIuMmMwLTguMSw2LjctMTEuOSwxNi43LTExLjljNC43LDAsOS4yLDEuMSwxMy4xLDIuOGwtMS40LDkuM2MtMi4zLTEtNi41LTItOS4yLTIKCQkJCWMtMS42LDAtMy40LDAuMS0zLjQsMS4yQzQ2Ni44LDE4Ni44LDQ4MS43LDE4NC40LDQ4MS43LDE5N3oiLz4KCQk8L2c+CgkJPGc+CgkJCTxnPgoJCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTE3Ni44LDIwOWgtMTYuNWMtMC42LDAtMS0wLjQtMS0xdi00My4zYzAtMC42LDAuNC0xLDEtMWgzMy45YzAuNiwwLDEsMC40LDEsMVYxNzdjMCwwLjYtMC40LDEtMSwxCgkJCQkJaC0xNi40djMuM2gxNC4yYzAuNiwwLDEsMC40LDEsMXYxMi43YzAsMC42LTAuNCwxLTEsMWgtMTQuMlYyMDhDMTc3LjgsMjA4LjYsMTc3LjQsMjA5LDE3Ni44LDIwOXogTTE2MS4zLDIwN2gxNC41di0xMS45CgkJCQkJYzAtMC42LDAuNC0xLDEtMWgxNC4ydi0xMC43aC0xNC4yYy0wLjYsMC0xLTAuNC0xLTFWMTc3YzAtMC42LDAuNC0xLDEtMWgxNi40di0xMC4zaC0zMS45VjIwN3oiLz4KCQkJPC9nPgoJCQk8Zz4KCQkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0yMTYuMiwyMDkuOGMtMTIuNywwLTIxLjUtNy43LTIxLjUtMTguOHM4LjktMTguOCwyMS41LTE4LjhjMTIuNiwwLDIxLjQsNy43LDIxLjQsMTguOAoJCQkJCVMyMjguOCwyMDkuOCwyMTYuMiwyMDkuOHogTTIxNi4yLDE3NC4zYy05LjQsMC0xOS41LDUuMy0xOS41LDE2LjhzMTAuMSwxNi44LDE5LjUsMTYuOGM5LjQsMCwxOS40LTUuMywxOS40LTE2LjgKCQkJCQlTMjI1LjYsMTc0LjMsMjE2LjIsMTc0LjN6IE0yMTYuMSwxOThjLTMuMywwLTUuOC0zLTUuOC03czIuNS03LDUuOC03czUuOCwzLDUuOCw3UzIxOS41LDE5OCwyMTYuMSwxOTh6IE0yMTYuMSwxODYuMQoJCQkJCWMtMi41LDAtMy44LDIuNi0zLjgsNXMxLjMsNSwzLjgsNXMzLjgtMi42LDMuOC01UzIxOC42LDE4Ni4xLDIxNi4xLDE4Ni4xeiIvPgoJCQk8L2c+CgkJCTxnPgoJCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTI1Ny4xLDIwOWgtMTYuM2MtMC42LDAtMS0wLjQtMS0xdi00Ny4zYzAtMC42LDAuNC0xLDEtMWgxNi4zYzAuNiwwLDEsMC40LDEsMVYyMDgKCQkJCQlDMjU4LjEsMjA4LjYsMjU3LjcsMjA5LDI1Ny4xLDIwOXogTTI0MS44LDIwN2gxNC4zdi00NS4zaC0xNC4zVjIwN3oiLz4KCQkJPC9nPgoJCQk8Zz4KCQkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0yNzkuNCwyMDloLTE2LjNjLTAuNiwwLTEtMC40LTEtMXYtNDcuM2MwLTAuNiwwLjQtMSwxLTFoMTYuM2MwLjYsMCwxLDAuNCwxLDFWMjA4CgkJCQkJQzI4MC40LDIwOC42LDI3OS45LDIwOSwyNzkuNCwyMDl6IE0yNjQuMSwyMDdoMTQuM3YtNDUuM2gtMTQuM1YyMDd6Ii8+CgkJCTwvZz4KCQkJPGc+CgkJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMzA0LDIwOS44Yy0xMi43LDAtMjEuNS03LjctMjEuNS0xOC44czguOS0xOC44LDIxLjUtMTguOGMxMi42LDAsMjEuNCw3LjcsMjEuNCwxOC44CgkJCQkJUzMxNi43LDIwOS44LDMwNCwyMDkuOHogTTMwNCwxNzQuM2MtOS40LDAtMTkuNSw1LjMtMTkuNSwxNi44czEwLjEsMTYuOCwxOS41LDE2LjhjOS40LDAsMTkuNC01LjMsMTkuNC0xNi44CgkJCQkJUzMxMy40LDE3NC4zLDMwNCwxNzQuM3ogTTMwNCwxOThjLTMuMywwLTUuOC0zLTUuOC03czIuNS03LDUuOC03czUuOCwzLDUuOCw3UzMwNy4zLDE5OCwzMDQsMTk4eiBNMzA0LDE4Ni4xCgkJCQkJYy0yLjUsMC0zLjgsMi42LTMuOCw1czEuMyw1LDMuOCw1czMuOC0yLjYsMy44LTVTMzA2LjUsMTg2LjEsMzA0LDE4Ni4xeiIvPgoJCQk8L2c+CgkJCTxnPgoJCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTM3NS4yLDIwOWgtMTUuOGMtMC40LDAtMC44LTAuMy0xLTAuN2wtMy42LTEyLjJsLTMuNywxMi4yYy0wLjEsMC40LTAuNSwwLjctMSwwLjdoLTE1LjcKCQkJCQljLTAuNCwwLTAuOC0wLjMtMS0wLjdsLTEwLjItMzMuOWMtMC4xLTAuMywwLTAuNiwwLjItMC45czAuNS0wLjQsMC44LTAuNGgxNi42YzAuNSwwLDAuOSwwLjMsMSwwLjhsMi41LDE0bDMuNi0xNAoJCQkJCWMwLjEtMC40LDAuNS0wLjcsMS0wLjdoMTEuNmMwLjUsMCwwLjgsMC4zLDEsMC43bDMuOSwxNC4zbDIuNy0xNC4yYzAuMS0wLjUsMC41LTAuOCwxLTAuOGgxNi40YzAuMywwLDAuNiwwLjEsMC44LDAuNAoJCQkJCXMwLjIsMC42LDAuMiwwLjlsLTEwLjIsMzMuOUMzNzYsMjA4LjcsMzc1LjYsMjA5LDM3NS4yLDIwOXogTTM2MC4xLDIwN2gxNC4zbDkuNi0zMS45aC0xNC4zbC0zLjMsMTcuNwoJCQkJCWMtMC4xLDAuNS0wLjUsMC44LTAuOSwwLjhjLTAuNSwwLTAuOS0wLjMtMS0wLjdsLTQuOS0xNy44aC0xMGwtNC42LDE3LjdjLTAuMSwwLjUtMC41LDAuOC0xLDAuN2MtMC41LDAtMC45LTAuNC0wLjktMC44CgkJCQkJbC0zLjEtMTcuN2gtMTQuNWw5LjYsMzEuOWgxNC4zbDQuNS0xNC43YzAuMS0wLjQsMC41LTAuNywxLTAuN2MwLDAsMCwwLDAsMGMwLjQsMCwwLjgsMC4zLDEsMC43TDM2MC4xLDIwN3oiLz4KCQkJPC9nPgoJCQk8Zz4KCQkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik00MjQuOSwyMDkuOGMtMTQuMywwLTIxLjktNi41LTIxLjktMTguOXYtMjYuMmMwLTAuNiwwLjQtMSwxLTFoMTYuN2MwLjYsMCwxLDAuNCwxLDF2MjYKCQkJCQljMCwzLjMsMC44LDQuNCwzLjIsNC40YzIuNCwwLDMuMi0xLjEsMy4yLTQuNHYtMjZjMC0wLjYsMC40LTEsMS0xaDE2LjdjMC42LDAsMSwwLjQsMSwxdjI2LjIKCQkJCQlDNDQ2LjgsMjAzLjMsNDM5LjIsMjA5LjgsNDI0LjksMjA5Ljh6IE00MDUsMTY1Ljd2MjUuMmMwLDExLjIsNi43LDE2LjksMTkuOSwxNi45YzEzLjIsMCwxOS45LTUuNywxOS45LTE2Ljl2LTI1LjJoLTE0Ljd2MjUKCQkJCQljMCwxLjcsMCw2LjQtNS4yLDYuNGMtNS4yLDAtNS4yLTQuNS01LjItNi40di0yNUg0MDV6Ii8+CgkJCTwvZz4KCQkJPGc+CgkJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNDY1LjMsMjA5LjhjLTUuNSwwLTExLTEuNC0xNS45LTRjLTAuNC0wLjItMC42LTAuNi0wLjUtMWwxLjUtOS43YzAuMS0wLjMsMC4zLTAuNiwwLjYtMC44CgkJCQkJYzAuMy0wLjEsMC43LTAuMSwxLDAuMWMzLjEsMi4xLDcuMiwzLjMsMTEsMy4zYzAuNiwwLDEtMC4xLDEuMy0wLjFjLTAuNS0wLjEtMS4yLTAuMy0xLjgtMC40Yy00LjMtMC45LTEyLjQtMi41LTEyLjQtMTIKCQkJCQljMC04LjIsNi41LTEyLjksMTcuNy0xMi45YzQuNSwwLDksMSwxMy40LDIuOGMwLjQsMC4yLDAuNywwLjYsMC42LDEuMWwtMS40LDkuM2MwLDAuMy0wLjIsMC42LTAuNSwwLjdzLTAuNiwwLjItMC45LDAKCQkJCQljLTIuMS0wLjktNi4yLTItOC43LTJjLTAuOSwwLTEuNSwwLTEuOSwwLjFjMC41LDAuMiwxLjMsMC4zLDIsMC41YzQuNCwwLjksMTIuNSwyLjYsMTIuNSwxMi4yCgkJCQkJQzQ4Mi43LDIwNS4yLDQ3Ni40LDIwOS44LDQ2NS4zLDIwOS44eiBNNDUxLDIwNC40YzQuNSwyLjMsOS40LDMuNSwxNC4zLDMuNWM1LjgsMCwxNS40LTEuNCwxNS40LTEwLjhjMC03LjktNi42LTkuMy0xMC45LTEwLjIKCQkJCQljLTIuNC0wLjUtNC4xLTAuOS00LjEtMi40YzAtMi4yLDIuOS0yLjIsNC40LTIuMmMyLjUsMCw1LjksMC44LDguNCwxLjdsMS4xLTcuM2MtMy45LTEuNi03LjktMi40LTExLjktMi40CgkJCQkJYy01LjksMC0xNS43LDEuNC0xNS43LDEwLjljMCw3LjgsNi41LDkuMSwxMC44LDEwYzIuMiwwLjUsMy44LDAuOCwzLjgsMi4yYzAsMC43LTAuNCwyLjMtMy43LDIuM2MtMy42LDAtNy42LTEtMTAuOC0yLjgKCQkJCQlMNDUxLDIwNC40eiIvPgoJCQk8L2c+CgkJPC9nPgoJCTxnPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNTI2LjcsMjgyLjlsNC43LDAuOGwtNC4yLDIzLjhsLTQuNy0wLjhMNTI2LjcsMjgyLjl6Ii8+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik01MzMuNSwyOTIuOWw0LjcsMC44bC0yLjcsMTUuM2wtNC43LTAuOEw1MzMuNSwyOTIuOXogTTUzNCwyODhjMC4xLTAuOCwwLjUtMS40LDEuMS0xLjhzMS4zLTAuNiwyLjEtMC41CgkJCQljMC44LDAuMSwxLjQsMC41LDEuOCwxLjFzMC42LDEuMywwLjUsMi4xYy0wLjEsMC44LTAuNSwxLjQtMS4xLDEuOHMtMS4zLDAuNi0yLjEsMC41Yy0wLjgtMC4xLTEuNC0wLjUtMS44LTEuMQoJCQkJUzUzMy45LDI4OC43LDUzNCwyODh6Ii8+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik01NDMuMywyODUuOGw0LjcsMC44bC0yLjYsMTQuNmw2LjMtNS4xbDUuOCwxbC03LjMsNS44bDQuOCw5LjVsLTYtMWwtMy44LTguN2wtMC4xLDBsLTEuNCw3LjhsLTQuNy0wLjgKCQkJCUw1NDMuMywyODUuOHoiLz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTU3MC44LDMxMi41Yy0wLjksMC44LTIsMS40LTMuMywxLjdjLTEuMiwwLjMtMi41LDAuNC0zLjcsMC4yYy0xLjItMC4yLTIuMy0wLjYtMy4yLTEuMgoJCQkJYy0xLTAuNi0xLjgtMS4zLTIuNC0yLjFjLTAuNi0wLjgtMS4xLTEuOC0xLjQtMi45cy0wLjMtMi4yLTAuMS0zLjRzMC42LTIuMywxLjItMy4yYzAuNi0wLjksMS40LTEuNiwyLjMtMi4yCgkJCQljMC45LTAuNiwxLjktMSwzLTEuMWMxLjEtMC4yLDIuMi0wLjIsMy40LDBjMS4xLDAuMiwyLjEsMC42LDIuOSwxLjFjMC44LDAuNSwxLjUsMS4yLDIsMmMwLjUsMC44LDAuOCwxLjcsMSwyLjgKCQkJCWMwLjIsMSwwLjEsMi4yLTAuMSwzLjRsLTAuMywxLjVsLTExLTEuOWMwLDAuOSwwLjMsMS43LDAuOCwyLjRjMC41LDAuNiwxLjMsMS4xLDIuMiwxLjJjMC44LDAuMSwxLjUsMC4xLDIuMS0wLjIKCQkJCWMwLjYtMC4zLDEuMS0wLjYsMS42LTEuMUw1NzAuOCwzMTIuNXogTTU2Ny45LDMwNWMwLjItMC44LDAtMS41LTAuNC0yLjJjLTAuNC0wLjctMS4xLTEuMS0yLTEuMmMtMC41LTAuMS0xLTAuMS0xLjQsMAoJCQkJcy0wLjgsMC4zLTEuMSwwLjVjLTAuMywwLjItMC42LDAuNS0wLjgsMC44Yy0wLjIsMC4zLTAuNCwwLjctMC41LDFMNTY3LjksMzA1eiIvPgoJCTwvZz4KCQk8Zz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTI2My41LDUzYy0wLjctMC41LTEuNC0wLjYtMi4zLTAuNGMtMC4zLDAuMS0wLjYsMC4yLTAuOCwwLjRjLTAuMiwwLjItMC4zLDAuNS0wLjIsMC44CgkJCQljMC4xLDAuMywwLjMsMC40LDAuNiwwLjVjMC4zLDAuMSwwLjcsMC4xLDEuMiwwLjFjMC41LDAsMSwwLDEuNS0wLjFjMC41LDAsMS4xLDAsMS42LDAuMmMwLjUsMC4xLDEsMC40LDEuNCwwLjcKCQkJCWMwLjQsMC4zLDAuNywwLjksMC45LDEuNmMwLjIsMC43LDAuMiwxLjQsMCwxLjljLTAuMiwwLjYtMC41LDEtMC45LDEuNWMtMC40LDAuNC0wLjksMC44LTEuNSwxYy0wLjYsMC4zLTEuMiwwLjUtMS44LDAuNwoJCQkJYy0wLjgsMC4yLTEuNiwwLjMtMi41LDAuM2MtMC45LDAtMS43LTAuMi0yLjQtMC42bDEuNS0yLjljMC40LDAuMywwLjksMC41LDEuMywwLjZjMC41LDAuMSwwLjksMC4xLDEuNS0wLjEKCQkJCWMwLjQtMC4xLDAuNy0wLjMsMS0wLjVzMC40LTAuNSwwLjMtMC44Yy0wLjEtMC4zLTAuMy0wLjUtMC42LTAuNWMtMC4zLTAuMS0wLjctMC4xLTEuMi0wLjFjLTAuNSwwLTEsMC0xLjUsMC4xCgkJCQljLTAuNSwwLTEuMSwwLTEuNi0wLjFjLTAuNS0wLjEtMS0wLjMtMS40LTAuN2MtMC40LTAuMy0wLjctMC45LTAuOS0xLjZjLTAuMi0wLjctMC4yLTEuMy0wLjEtMS44YzAuMS0wLjYsMC40LTEsMC44LTEuNQoJCQkJczAuOC0wLjgsMS4zLTEuMWMwLjUtMC4zLDEuMS0wLjUsMS43LTAuN2MwLjctMC4yLDEuNS0wLjMsMi4zLTAuM2MwLjgsMCwxLjYsMC4yLDIuMiwwLjZMMjYzLjUsNTN6Ii8+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0yNjguOSw0MS4zbDIuMSw3LjhsMCwwYzAtMC4yLDAuMS0wLjUsMC4yLTAuOGMwLjEtMC4zLDAuMy0wLjUsMC41LTAuOGMwLjItMC4yLDAuNS0wLjUsMC44LTAuNwoJCQkJczAuNy0wLjQsMS4xLTAuNWMwLjktMC4yLDEuNi0wLjMsMi4yLTAuMmMwLjYsMC4xLDEuMSwwLjQsMS42LDAuOGMwLjQsMC40LDAuOCwwLjksMS4xLDEuNXMwLjUsMS4zLDAuNywyLjFsMS43LDYuMmwtMy41LDAuOQoJCQkJbC0xLjUtNS41Yy0wLjEtMC4zLTAuMi0wLjctMC4zLTFzLTAuMy0wLjYtMC41LTAuOWMtMC4yLTAuMy0wLjQtMC41LTAuNy0wLjZjLTAuMy0wLjEtMC43LTAuMS0xLjEsMGMtMC40LDAuMS0wLjgsMC4zLTEsMC41CgkJCQljLTAuMiwwLjItMC40LDAuNS0wLjUsMC44Yy0wLjEsMC4zLTAuMSwwLjYsMCwxYzAsMC40LDAuMSwwLjcsMC4yLDEuMWwxLjUsNS42bC0zLjUsMC45bC00LjctMTcuNUwyNjguOSw0MS4zeiIvPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMjkwLjIsNTIuOUwyOTAuMiw1Mi45Yy0wLjMsMC43LTAuNywxLjMtMS4yLDEuN2MtMC42LDAuNC0xLjIsMC43LTEuOSwwLjljLTAuNSwwLjEtMS4xLDAuMi0xLjYsMC4yCgkJCQljLTAuNSwwLTEtMC4xLTEuNS0wLjNjLTAuNS0wLjItMC44LTAuNS0xLjItMC45Yy0wLjMtMC40LTAuNi0wLjgtMC43LTEuNGMtMC4yLTAuNi0wLjItMS4yLTAuMS0xLjdzMC4zLTEsMC43LTEuNAoJCQkJYzAuMy0wLjQsMC43LTAuOCwxLjItMS4xYzAuNS0wLjMsMS0wLjYsMS41LTAuOHMxLjEtMC40LDEuNy0wLjZjMC42LTAuMiwxLjEtMC4zLDEuNi0wLjRjLTAuMi0wLjYtMC41LTEtMS4xLTEuMwoJCQkJYy0wLjUtMC4yLTEuMS0wLjMtMS43LTAuMWMtMC42LDAuMi0xLjEsMC40LTEuNSwwLjhzLTAuNywwLjgtMSwxLjNsLTIuNC0xLjRjMC41LTAuOCwxLjEtMS40LDEuOS0yczEuNi0wLjksMi42LTEuMgoJCQkJYzEtMC4zLDEuOS0wLjQsMi42LTAuM2MwLjcsMC4xLDEuNCwwLjMsMS45LDAuN2MwLjUsMC40LDEsMC45LDEuMywxLjZjMC4zLDAuNywwLjYsMS41LDAuOSwyLjRsMS41LDUuN2wtMy4yLDAuOUwyOTAuMiw1Mi45egoJCQkJIE0yODguNCw0OS42Yy0wLjMsMC4xLTAuNiwwLjItMSwwLjNjLTAuNCwwLjEtMC43LDAuMy0xLjEsMC41cy0wLjYsMC41LTAuOCwwLjdjLTAuMiwwLjMtMC4yLDAuNi0wLjEsMWMwLjEsMC40LDAuNCwwLjcsMC44LDAuOAoJCQkJYzAuNCwwLjEsMC44LDAuMSwxLjIsMGMwLjMtMC4xLDAuNy0wLjIsMC45LTAuNGMwLjMtMC4yLDAuNS0wLjQsMC43LTAuNmMwLjItMC4yLDAuMy0wLjUsMC40LTAuOGMwLjEtMC4zLDAuMS0wLjYsMC0xbC0wLjItMC43CgkJCQlMMjg4LjQsNDkuNnoiLz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTI5My4yLDQxLjVsMy41LTAuOWwwLjUsMS44bDAsMGMwLjItMC44LDAuNS0xLjQsMC45LTEuOXMxLTAuOCwxLjgtMWMwLjItMC4xLDAuNC0wLjEsMC42LTAuMQoJCQkJYzAuMiwwLDAuNC0wLjEsMC42LTAuMWwwLjksMy4yYy0wLjMsMC0wLjUsMC0wLjgsMGMtMC4yLDAtMC41LDAuMS0wLjgsMC4xYy0wLjcsMC4yLTEuMiwwLjQtMS41LDAuN2MtMC4zLDAuMy0wLjYsMC42LTAuNywxCgkJCQljLTAuMSwwLjQtMC4xLDAuOC0wLjEsMS4zYzAuMSwwLjUsMC4yLDEsMC4zLDEuNmwxLjMsNC43bC0zLjUsMC45TDI5My4yLDQxLjV6Ii8+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0zMTUuNyw0NS41Yy0wLjQsMC45LTAuOSwxLjYtMS43LDIuMmMtMC43LDAuNi0xLjYsMS0yLjUsMS4zYy0wLjksMC4yLTEuNywwLjMtMi42LDAuMgoJCQkJYy0wLjgtMC4xLTEuNi0wLjMtMi4zLTAuN2MtMC43LTAuNC0xLjMtMC45LTEuOC0xLjVzLTAuOS0xLjQtMS4xLTIuM3MtMC4zLTEuOC0wLjItMi42YzAuMS0wLjgsMC40LTEuNiwwLjgtMi4yCgkJCQljMC40LTAuNywxLTEuMiwxLjctMS43YzAuNy0wLjUsMS41LTAuOCwyLjMtMS4xYzAuOC0wLjIsMS42LTAuMywyLjMtMC4yYzAuNywwLjEsMS40LDAuNCwyLDAuN2MwLjYsMC40LDEuMSwwLjksMS42LDEuNgoJCQkJYzAuNCwwLjcsMC44LDEuNCwxLDIuM2wwLjMsMS4xbC04LjEsMi4yYzAuMywwLjYsMC44LDEuMSwxLjMsMS4zYzAuNiwwLjMsMS4yLDAuMywxLjksMC4xYzAuNi0wLjIsMS0wLjQsMS4zLTAuOAoJCQkJYzAuMy0wLjQsMC42LTAuOCwwLjgtMS4zTDMxNS43LDQ1LjV6IE0zMTEuNCw0MS4zYy0wLjEtMC42LTAuNS0xLTEtMS40Yy0wLjUtMC4zLTEuMS0wLjQtMS43LTAuMmMtMC40LDAuMS0wLjcsMC4zLTEsMC41CgkJCQlzLTAuNSwwLjQtMC42LDAuN2MtMC4yLDAuMi0wLjMsMC41LTAuMywwLjhjMCwwLjMsMCwwLjYsMCwwLjlMMzExLjQsNDEuM3oiLz4KCQk8L2c+CgkJPGc+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik00Ni45LDE2MS4xYzAtMC42LDAuMS0xLjIsMC4zLTEuNmMwLjItMC40LDAuNS0wLjksMC45LTEuMmMwLjYtMC42LDEuMS0xLjEsMS42LTEuNXMwLjktMC44LDEuMy0xLjIKCQkJCWMwLjQtMC40LDAuNi0wLjcsMC44LTEuMWMwLjItMC4zLDAuMy0wLjcsMC4zLTFjMC0wLjctMC4yLTEuMy0wLjctMS42Yy0wLjQtMC40LTEtMC42LTEuNi0wLjZjLTEsMC0xLjgsMC4zLTIuMywwLjgKCQkJCWMtMC41LDAuNi0wLjgsMS4yLTAuOSwybC00LjktMC4zYzAuMi0yLjMsMS4xLTQsMi41LTUuMmMxLjQtMS4yLDMuMy0xLjgsNS41LTEuOGMxLDAsMS45LDAuMSwyLjgsMC40YzAuOSwwLjMsMS42LDAuNywyLjMsMS4yCgkJCQljMC43LDAuNSwxLjIsMS4yLDEuNiwyYzAuNCwwLjgsMC42LDEuNywwLjYsMi43YzAsMC42LTAuMSwxLjItMC4yLDEuN2MtMC4xLDAuNS0wLjMsMS0wLjcsMS41Yy0wLjMsMC41LTAuNywxLTEuMiwxLjUKCQkJCWMtMC41LDAuNS0xLjEsMS4xLTEuOSwxLjZjLTAuNSwwLjQtMC44LDAuOC0xLDEuMXMtMC4zLDAuNy0wLjMsMS4xdjAuOWgtNC44VjE2MS4xeiBNNDYuNCwxNjcuMmMwLTAuNCwwLjEtMC44LDAuMi0xLjIKCQkJCXMwLjQtMC43LDAuNi0wLjljMC4zLTAuMywwLjYtMC41LDAuOS0wLjZjMC40LTAuMSwwLjctMC4yLDEuMi0wLjJzMC44LDAuMSwxLjIsMC4yYzAuNCwwLjEsMC43LDAuNCwwLjksMC42CgkJCQljMC4zLDAuMywwLjUsMC42LDAuNiwwLjljMC4xLDAuNCwwLjIsMC43LDAuMiwxLjJzLTAuMSwwLjgtMC4yLDEuMmMtMC4xLDAuNC0wLjQsMC43LTAuNiwwLjljLTAuMywwLjMtMC42LDAuNS0wLjksMC42CgkJCQljLTAuNCwwLjEtMC43LDAuMi0xLjIsMC4ycy0wLjgtMC4xLTEuMi0wLjJjLTAuNC0wLjEtMC43LTAuNC0wLjktMC42cy0wLjUtMC42LTAuNi0wLjlDNDYuNCwxNjgsNDYuNCwxNjcuNyw0Ni40LDE2Ny4yeiIvPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNjAsMTY3LjJjMC0wLjQsMC4xLTAuOCwwLjItMS4yczAuNC0wLjcsMC42LTAuOWMwLjMtMC4zLDAuNi0wLjUsMC45LTAuNmMwLjQtMC4xLDAuNy0wLjIsMS4yLTAuMgoJCQkJczAuOCwwLjEsMS4yLDAuMmMwLjQsMC4xLDAuNywwLjQsMC45LDAuNmMwLjMsMC4zLDAuNSwwLjYsMC42LDAuOWMwLjEsMC40LDAuMiwwLjcsMC4yLDEuMnMtMC4xLDAuOC0wLjIsMS4yCgkJCQljLTAuMSwwLjQtMC40LDAuNy0wLjYsMC45Yy0wLjMsMC4zLTAuNiwwLjUtMC45LDAuNmMtMC40LDAuMS0wLjcsMC4yLTEuMiwwLjJzLTAuOC0wLjEtMS4yLTAuMmMtMC40LTAuMS0wLjctMC40LTAuOS0wLjYKCQkJCXMtMC41LTAuNi0wLjYtMC45QzYwLjEsMTY4LDYwLDE2Ny43LDYwLDE2Ny4yeiBNNjUuNCwxNjIuNWgtNC44di0xNS4yaDQuOFYxNjIuNXoiLz4KCQk8L2c+CgkJPGc+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik01NjAuMywxMTYuNGwzLjMtMC45bDAuNCwxLjVsMCwwYzAuMS0wLjIsMC4xLTAuNSwwLjMtMC44czAuMy0wLjUsMC42LTAuOGMwLjItMC4yLDAuNS0wLjUsMC44LTAuNwoJCQkJYzAuMy0wLjIsMC43LTAuNCwxLjEtMC41YzAuOS0wLjIsMS42LTAuMywyLjItMC4yYzAuNiwwLjEsMS4xLDAuNCwxLjYsMC44czAuOCwwLjksMS4xLDEuNWMwLjMsMC42LDAuNSwxLjMsMC43LDIuMWwxLjcsNi4yCgkJCQlsLTMuNSwwLjlsLTEuNS01LjVjLTAuMS0wLjMtMC4yLTAuNy0wLjMtMXMtMC4zLTAuNi0wLjUtMC45Yy0wLjItMC4zLTAuNC0wLjUtMC43LTAuNmMtMC4zLTAuMS0wLjctMC4xLTEuMSwwCgkJCQljLTAuNCwwLjEtMC44LDAuMy0xLDAuNWMtMC4yLDAuMi0wLjQsMC41LTAuNSwwLjhjLTAuMSwwLjMtMC4xLDAuNiwwLDFzMC4xLDAuNywwLjIsMS4xbDEuNSw1LjZsLTMuNSwwLjlMNTYwLjMsMTE2LjR6Ii8+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik01ODYuNywxMTkuM2MtMC40LDAuOS0wLjksMS42LTEuNywyLjJjLTAuNywwLjYtMS42LDEtMi41LDEuM2MtMC45LDAuMi0xLjcsMC4zLTIuNiwwLjIKCQkJCWMtMC44LTAuMS0xLjYtMC4zLTIuMy0wLjdjLTAuNy0wLjQtMS4zLTAuOS0xLjgtMS41cy0wLjktMS40LTEuMS0yLjNzLTAuMy0xLjgtMC4yLTIuNmMwLjEtMC44LDAuNC0xLjYsMC44LTIuMgoJCQkJYzAuNC0wLjcsMS0xLjIsMS43LTEuN2MwLjctMC41LDEuNS0wLjgsMi4zLTEuMWMwLjgtMC4yLDEuNi0wLjMsMi4zLTAuMmMwLjcsMC4xLDEuNCwwLjQsMiwwLjdjMC42LDAuNCwxLjEsMC45LDEuNiwxLjYKCQkJCWMwLjQsMC43LDAuOCwxLjQsMSwyLjNsMC4zLDEuMWwtOC4xLDIuMmMwLjMsMC42LDAuOCwxLjEsMS4zLDEuM2MwLjYsMC4zLDEuMiwwLjMsMS45LDAuMWMwLjYtMC4yLDEtMC40LDEuMy0wLjgKCQkJCWMwLjMtMC40LDAuNi0wLjgsMC44LTEuM0w1ODYuNywxMTkuM3ogTTU4Mi40LDExNS4yYy0wLjEtMC42LTAuNS0xLTEtMS40cy0xLjEtMC40LTEuNy0wLjJjLTAuNCwwLjEtMC43LDAuMy0xLDAuNQoJCQkJcy0wLjUsMC40LTAuNiwwLjdjLTAuMiwwLjItMC4zLDAuNS0wLjMsMC44YzAsMC4zLDAsMC42LDAsMC45TDU4Mi40LDExNS4yeiIvPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNTg1LjEsMTA5LjhsMy43LTFsNC4yLDYuNWwwLDBsMC03LjZsMy44LTFsNCw2LjVsMCwwbDAuMi03LjZsMy41LTAuOWwtMSwxMi4zbC0zLjQsMC45bC00LjMtNi45bDAsMAoJCQkJbC0wLjEsOGwtMy41LDAuOUw1ODUuMSwxMDkuOHoiLz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTYxMywxMDUuOGMtMC43LTAuNS0xLjQtMC42LTIuMy0wLjRjLTAuMywwLjEtMC42LDAuMi0wLjgsMC40Yy0wLjIsMC4yLTAuMywwLjUtMC4yLDAuOAoJCQkJYzAuMSwwLjMsMC4zLDAuNCwwLjYsMC41YzAuMywwLjEsMC43LDAuMSwxLjIsMC4xYzAuNSwwLDEsMCwxLjUtMC4xYzAuNSwwLDEuMSwwLDEuNiwwLjJjMC41LDAuMSwxLDAuNCwxLjQsMC43CgkJCQljMC40LDAuMywwLjcsMC45LDAuOSwxLjZjMC4yLDAuNywwLjIsMS40LDAsMS45Yy0wLjIsMC42LTAuNSwxLTAuOSwxLjVjLTAuNCwwLjQtMC45LDAuOC0xLjUsMWMtMC42LDAuMy0xLjIsMC41LTEuOCwwLjcKCQkJCWMtMC44LDAuMi0xLjYsMC4zLTIuNSwwLjNjLTAuOSwwLTEuNi0wLjItMi40LTAuNmwxLjUtMi45YzAuNCwwLjMsMC45LDAuNSwxLjMsMC42YzAuNCwwLjEsMC45LDAuMSwxLjUtMC4xCgkJCQljMC40LTAuMSwwLjgtMC4zLDEtMC41YzAuMy0wLjIsMC40LTAuNSwwLjMtMC44Yy0wLjEtMC4zLTAuMy0wLjUtMC42LTAuNWMtMC4zLTAuMS0wLjctMC4xLTEuMi0wLjFjLTAuNSwwLTEsMC0xLjUsMC4xCgkJCQlzLTEuMSwwLTEuNi0wLjFjLTAuNS0wLjEtMS0wLjMtMS40LTAuN2MtMC40LTAuMy0wLjctMC45LTAuOS0xLjZjLTAuMi0wLjctMC4yLTEuMy0wLjEtMS44YzAuMS0wLjYsMC40LTEsMC44LTEuNQoJCQkJYzAuNC0wLjQsMC44LTAuOCwxLjMtMS4xYzAuNS0wLjMsMS4xLTAuNSwxLjctMC43YzAuNy0wLjIsMS41LTAuMywyLjMtMC4zYzAuOCwwLDEuNiwwLjIsMi4yLDAuNkw2MTMsMTA1Ljh6Ii8+CgkJPC9nPgoJCTxnPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMjcuMiwzOC4yYy0yLjctOS45LDMuOC0xOS45LDEzLTIyLjNjOS0yLjQsMTYuOSwyLjIsMTkuMSwxMC41YzIsNy42LTEuOCwxMi4zLTYsMTMuNAoJCQkJYy0zLjMsMC45LTQuOC0xLjItNS40LTIuMmMtMC45LDIuNi0yLjgsNC40LTUuMiw1Yy00LjYsMS4yLTguMi0xLjUtOS4zLTUuN2MtMS42LTUuOCwxLjYtMTEuOCw2LjgtMTMuMWMyLjUtMC43LDQuOCwwLDYuMywxLjQKCQkJCWwtMC4yLTIuM2w1LjItMS40bDAuOCwxMS4xYzAuMSwxLjEsMC42LDMuMywyLjQsMi44QzU3LDM0LjgsNTguNCwzMiw1NywyN2MtMi03LjUtOC41LTExLjEtMTYuNC05Yy04LjIsMi4yLTEzLjUsMTEuMS0xMS4zLDE5LjUKCQkJCWMyLjEsNy43LDkuNywxMS44LDE3LjMsOS44YzIuOS0wLjgsNS40LTIuNCw3LjQtNC41bDEuNiwxLjRjLTIuNCwyLjUtNS4yLDQuMy04LjUsNS4yQzM4LDUxLjgsMjkuNSw0Ni42LDI3LjIsMzguMnogTTQ2LjYsMzAuNgoJCQkJYy0wLjUtMi0yLjEtMy4zLTQuMi0yLjdjLTIuOSwwLjgtNC4yLDMuOS0zLjQsNy4xYzAuNiwyLjIsMi4zLDMuMyw0LjMsMi44QzQ1LjgsMzcuMSw0Ny43LDM0LjQsNDYuNiwzMC42eiIvPgoJCTwvZz4KCQk8Zz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTEwNy4xLDMzMy4xYy0wLjYtMC42LTEuMy0wLjktMi4yLTAuOGMtMC4zLDAtMC42LDAuMS0wLjksMC4zYy0wLjMsMC4yLTAuNCwwLjQtMC40LDAuOAoJCQkJYzAsMC4zLDAuMiwwLjUsMC41LDAuNmMwLjMsMC4xLDAuNywwLjIsMS4yLDAuM3MxLDAuMSwxLjUsMC4yYzAuNSwwLjEsMSwwLjIsMS41LDAuNGMwLjUsMC4yLDAuOSwwLjUsMS4yLDAuOQoJCQkJYzAuMywwLjQsMC41LDEsMC42LDEuN2MwLjEsMC43LDAsMS40LTAuMywxLjljLTAuMywwLjUtMC43LDAuOS0xLjIsMS4zYy0wLjUsMC4zLTEsMC42LTEuNywwLjhjLTAuNiwwLjItMS4zLDAuMy0xLjksMC4zCgkJCQljLTAuOCwwLjEtMS42LDAtMi41LTAuMWMtMC45LTAuMi0xLjYtMC41LTIuMi0xbDItMi42YzAuNCwwLjQsMC44LDAuNywxLjIsMC44czAuOSwwLjIsMS41LDAuMmMwLjQsMCwwLjgtMC4xLDEuMS0wLjMKCQkJCWMwLjMtMC4xLDAuNS0wLjQsMC40LTAuN2MwLTAuMy0wLjItMC41LTAuNS0wLjZjLTAuMy0wLjEtMC43LTAuMi0xLjItMC4zYy0wLjUtMC4xLTEtMC4xLTEuNS0wLjJzLTEtMC4yLTEuNS0wLjQKCQkJCWMtMC41LTAuMi0wLjktMC41LTEuMi0wLjljLTAuMy0wLjQtMC41LTEtMC42LTEuN2MtMC4xLTAuNywwLTEuMywwLjMtMS44YzAuMi0wLjUsMC42LTEsMS0xLjNjMC40LTAuNCwwLjktMC42LDEuNS0wLjgKCQkJCWMwLjYtMC4yLDEuMi0wLjMsMS44LTAuNGMwLjgtMC4xLDEuNSwwLDIuMywwLjFjMC44LDAuMiwxLjUsMC41LDIuMSwxTDEwNy4xLDMzMy4xeiIvPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMTIzLjYsMzM5LjlsLTMuNCwwLjNsLTAuMS0xLjZsMCwwYy0wLjEsMC4yLTAuMywwLjUtMC40LDAuN2MtMC4yLDAuMi0wLjQsMC41LTAuNywwLjcKCQkJCWMtMC4zLDAuMi0wLjYsMC40LTAuOSwwLjVjLTAuNCwwLjEtMC44LDAuMi0xLjIsMC4zYy0wLjksMC4xLTEuNywwLTIuMi0wLjJjLTAuNi0wLjItMS4xLTAuNi0xLjQtMWMtMC40LTAuNS0wLjYtMS0wLjgtMS43CgkJCQljLTAuMi0wLjctMC4zLTEuNC0wLjMtMi4ybC0wLjYtNi40bDMuNi0wLjNsMC41LDUuN2MwLDAuMywwLjEsMC43LDAuMSwxYzAuMSwwLjQsMC4yLDAuNywwLjMsMWMwLjEsMC4zLDAuNCwwLjUsMC42LDAuNwoJCQkJYzAuMywwLjIsMC42LDAuMiwxLjEsMC4yYzAuNSwwLDAuOC0wLjIsMS4xLTAuM2MwLjMtMC4yLDAuNS0wLjQsMC42LTAuN2MwLjEtMC4zLDAuMi0wLjYsMC4yLTFjMC0wLjQsMC0wLjcsMC0xLjFsLTAuNS01LjgKCQkJCWwzLjYtMC4zTDEyMy42LDMzOS45eiIvPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMTI0LjgsMzIxLjZsMy42LTAuM2wwLjcsNy43bDAsMGMwLjQtMC42LDAuOS0xLDEuNS0xLjNjMC42LTAuMywxLjMtMC41LDIuMS0wLjVjMC44LTAuMSwxLjYsMCwyLjMsMC4zCgkJCQlzMS4zLDAuNywxLjgsMS4yYzAuNSwwLjUsMC45LDEuMiwxLjIsMS45YzAuMywwLjcsMC41LDEuNSwwLjYsMi4zYzAuMSwwLjksMCwxLjctMC4yLDIuNWMtMC4yLDAuOC0wLjUsMS40LTEsMgoJCQkJYy0wLjUsMC42LTEsMS0xLjcsMS40Yy0wLjcsMC40LTEuNCwwLjYtMi4zLDAuNmMtMC40LDAtMC44LDAtMS4yLTAuMWMtMC40LTAuMS0wLjctMC4yLTEuMS0wLjNjLTAuMy0wLjEtMC42LTAuMy0wLjktMC41CgkJCQljLTAuMi0wLjItMC41LTAuNC0wLjYtMC42bDAsMGwwLjEsMS41bC0zLjMsMC4zTDEyNC44LDMyMS42eiBNMTI5LjIsMzMzLjVjMC4xLDAuOSwwLjQsMS42LDAuOSwyLjFjMC41LDAuNSwxLjMsMC43LDIuMiwwLjYKCQkJCWMwLjktMC4xLDEuNi0wLjQsMi0xYzAuNS0wLjYsMC42LTEuMywwLjYtMi4yYy0wLjEtMC45LTAuNC0xLjYtMC45LTIuMWMtMC41LTAuNS0xLjMtMC43LTIuMi0wLjZjLTAuOSwwLjEtMS42LDAuNC0yLDEKCQkJCVMxMjkuMSwzMzIuNywxMjkuMiwzMzMuNXoiLz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTE0Ni45LDMyOS42Yy0wLjYtMC42LTEuMy0wLjktMi4yLTAuOGMtMC4zLDAtMC42LDAuMS0wLjksMC4zYy0wLjMsMC4yLTAuNCwwLjQtMC40LDAuOAoJCQkJYzAsMC4zLDAuMiwwLjUsMC41LDAuNmMwLjMsMC4xLDAuNywwLjIsMS4yLDAuM2MwLjUsMC4xLDEsMC4xLDEuNSwwLjJjMC41LDAuMSwxLDAuMiwxLjUsMC40czAuOSwwLjUsMS4yLDAuOQoJCQkJYzAuMywwLjQsMC41LDEsMC42LDEuN2MwLjEsMC44LDAsMS40LTAuMywxLjljLTAuMywwLjUtMC43LDAuOS0xLjIsMS4zYy0wLjUsMC4zLTEsMC42LTEuNywwLjhjLTAuNiwwLjItMS4zLDAuMy0xLjksMC4zCgkJCQljLTAuOCwwLjEtMS42LDAtMi41LTAuMWMtMC45LTAuMi0xLjYtMC41LTIuMi0xbDItMi42YzAuNCwwLjQsMC44LDAuNywxLjIsMC44czAuOSwwLjIsMS41LDAuMmMwLjQsMCwwLjgtMC4xLDEuMS0wLjMKCQkJCXMwLjUtMC40LDAuNC0wLjdjMC0wLjMtMC4yLTAuNS0wLjUtMC42Yy0wLjMtMC4xLTAuNy0wLjItMS4yLTAuM2MtMC41LTAuMS0xLTAuMS0xLjUtMC4yYy0wLjUtMC4xLTEtMC4yLTEuNS0wLjQKCQkJCWMtMC41LTAuMi0wLjktMC41LTEuMi0wLjljLTAuMy0wLjQtMC41LTEtMC42LTEuN2MtMC4xLTAuNywwLTEuMywwLjMtMS44YzAuMi0wLjUsMC42LTEsMS0xLjNjMC40LTAuNCwwLjktMC42LDEuNS0wLjgKCQkJCWMwLjYtMC4yLDEuMi0wLjMsMS44LTAuNGMwLjgtMC4xLDEuNSwwLDIuMywwLjFjMC44LDAuMiwxLjUsMC41LDIuMSwxTDE0Ni45LDMyOS42eiIvPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMTU5LjIsMzI4LjhjLTAuMi0wLjItMC41LTAuNC0wLjgtMC42Yy0wLjMtMC4xLTAuNy0wLjItMS4xLTAuMmMtMC45LDAuMS0xLjYsMC40LTIsMQoJCQkJYy0wLjUsMC42LTAuNiwxLjMtMC42LDIuMmMwLjEsMC45LDAuNCwxLjYsMC45LDIuMWMwLjYsMC41LDEuMywwLjcsMi4yLDAuNmMwLjQsMCwwLjctMC4yLDEtMC40YzAuMy0wLjIsMC41LTAuNCwwLjctMC43CgkJCQlsMi42LDIuM2MtMC41LDAuNi0xLjEsMS4xLTEuOSwxLjRjLTAuNywwLjMtMS40LDAuNS0yLjEsMC41Yy0wLjksMC4xLTEuNywwLTIuNi0wLjJjLTAuOC0wLjItMS41LTAuNi0yLjItMS4xCgkJCQljLTAuNi0wLjUtMS4xLTEuMS0xLjUtMS44Yy0wLjQtMC43LTAuNi0xLjUtMC43LTIuNWMtMC4xLTAuOSwwLTEuOCwwLjMtMi42YzAuMy0wLjgsMC43LTEuNSwxLjItMmMwLjUtMC42LDEuMi0xLjEsMS45LTEuNAoJCQkJYzAuOC0wLjQsMS42LTAuNiwyLjUtMC43YzAuNy0wLjEsMS40LDAsMi4yLDAuMmMwLjgsMC4yLDEuNSwwLjUsMi4xLDFMMTU5LjIsMzI4Ljh6Ii8+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0xNjIuNywzMjQuOGwzLjYtMC4zbDAuMiwxLjlsMCwwYzAuMy0wLjgsMC43LTEuMywxLjItMS43YzAuNS0wLjQsMS4xLTAuNiwxLjktMC43YzAuMiwwLDAuNCwwLDAuNiwwCgkJCQljMC4yLDAsMC40LDAsMC42LDBsMC4zLDMuM2MtMC4zLTAuMS0wLjUtMC4xLTAuOC0wLjFjLTAuMywwLTAuNSwwLTAuOCwwYy0wLjcsMC4xLTEuMiwwLjItMS42LDAuNGMtMC40LDAuMi0wLjcsMC41LTAuOCwwLjkKCQkJCWMtMC4yLDAuNC0wLjMsMC44LTAuMywxLjNjMCwwLjUsMCwxLDAsMS42bDAuNCw0LjlsLTMuNiwwLjNMMTYyLjcsMzI0Ljh6Ii8+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0xNzEuOCwzMjAuM2MwLTAuNiwwLjEtMS4xLDAuNS0xLjVjMC40LTAuNCwwLjgtMC43LDEuNC0wLjdjMC42LTAuMSwxLjEsMC4xLDEuNSwwLjUKCQkJCWMwLjQsMC40LDAuNywwLjgsMC43LDEuNGMwLjEsMC42LTAuMSwxLjEtMC41LDEuNWMtMC40LDAuNC0wLjgsMC43LTEuNCwwLjdjLTAuNiwwLTEuMS0wLjEtMS41LTAuNQoJCQkJQzE3Mi4xLDMyMS4zLDE3MS45LDMyMC45LDE3MS44LDMyMC4zeiBNMTcyLjUsMzIzLjlsMy42LTAuM2wxLDExLjZsLTMuNiwwLjNMMTcyLjUsMzIzLjl6Ii8+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0xNzguNCwzMTYuOWwzLjYtMC4zbDAuNyw3LjdsMCwwYzAuNC0wLjYsMC45LTEsMS41LTEuM2MwLjYtMC4zLDEuMy0wLjUsMi4xLTAuNWMwLjgtMC4xLDEuNiwwLDIuMywwLjMKCQkJCWMwLjcsMC4zLDEuMywwLjcsMS44LDEuMmMwLjUsMC41LDAuOSwxLjIsMS4yLDEuOWMwLjMsMC43LDAuNSwxLjUsMC42LDIuM2MwLjEsMC45LDAsMS43LTAuMiwyLjVjLTAuMiwwLjgtMC41LDEuNC0xLDIKCQkJCWMtMC41LDAuNi0xLDEtMS43LDEuNGMtMC43LDAuNC0xLjQsMC42LTIuMywwLjZjLTAuNCwwLTAuOCwwLTEuMi0wLjFjLTAuNC0wLjEtMC43LTAuMi0xLjEtMC4zYy0wLjMtMC4xLTAuNi0wLjMtMC45LTAuNQoJCQkJYy0wLjItMC4yLTAuNS0wLjQtMC42LTAuNmwwLDBsMC4xLDEuNUwxODAsMzM1TDE3OC40LDMxNi45eiBNMTgyLjgsMzI4LjljMC4xLDAuOSwwLjQsMS42LDAuOSwyLjFjMC41LDAuNSwxLjMsMC43LDIuMiwwLjYKCQkJCXMxLjYtMC40LDItMWMwLjUtMC42LDAuNi0xLjMsMC42LTIuMmMtMC4xLTAuOS0wLjQtMS42LTAuOS0yLjFzLTEuMy0wLjctMi4yLTAuNmMtMC45LDAuMS0xLjYsMC40LTIsMVMxODIuNywzMjgsMTgyLjgsMzI4Ljl6IgoJCQkJLz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTIwNS40LDMzMC43Yy0wLjUsMC44LTEuMiwxLjQtMiwxLjljLTAuOCwwLjUtMS43LDAuOC0yLjcsMC44Yy0wLjksMC4xLTEuNywwLTIuNi0wLjIKCQkJCWMtMC44LTAuMi0xLjUtMC42LTIuMi0xLjFjLTAuNi0wLjUtMS4xLTEuMS0xLjUtMS44Yy0wLjQtMC43LTAuNi0xLjUtMC43LTIuNWMtMC4xLTAuOSwwLTEuOCwwLjMtMi42YzAuMy0wLjgsMC43LTEuNSwxLjItMgoJCQkJYzAuNS0wLjYsMS4yLTEuMSwxLjktMS40YzAuOC0wLjQsMS42LTAuNiwyLjUtMC43YzAuOC0wLjEsMS42LDAsMi4zLDAuMmMwLjcsMC4yLDEuMywwLjYsMS44LDEuMWMwLjUsMC41LDAuOSwxLjEsMS4zLDEuOAoJCQkJYzAuMywwLjcsMC41LDEuNiwwLjYsMi41bDAuMSwxLjFsLTguMywwLjdjMC4yLDAuNywwLjYsMS4yLDEuMSwxLjZjMC41LDAuNCwxLjEsMC41LDEuOCwwLjVjMC42LTAuMSwxLjEtMC4yLDEuNS0wLjUKCQkJCWMwLjQtMC4zLDAuNy0wLjcsMS0xLjFMMjA1LjQsMzMwLjd6IE0yMDIsMzI1LjljMC0wLjYtMC4zLTEuMS0wLjctMS41Yy0wLjUtMC40LTEtMC42LTEuNy0wLjVjLTAuNCwwLTAuNywwLjEtMSwwLjMKCQkJCXMtMC41LDAuMy0wLjcsMC42Yy0wLjIsMC4yLTAuMywwLjUtMC40LDAuN2MtMC4xLDAuMy0wLjEsMC42LTAuMSwwLjhMMjAyLDMyNS45eiIvPgoJCTwvZz4KCQk8Zz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTEyOCw0M2MtNy4yLDAtMTMtNS44LTEzLTEzczUuOC0xMywxMy0xM3MxMyw1LjgsMTMsMTNTMTM1LjIsNDMsMTI4LDQzeiBNMTI4LDE5Yy02LjEsMC0xMSw0LjktMTEsMTEKCQkJCXM0LjksMTEsMTEsMTFzMTEtNC45LDExLTExUzEzNC4xLDE5LDEyOCwxOXoiLz4KCQk8L2c+CgkJPGc+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0xMjgsMzguNWMtMS44LDAtMy41LTAuOC00LjgtMi40Yy0wLjQtMC40LTAuMy0xLjEsMC4xLTEuNGMwLjQtMC40LDEuMS0wLjMsMS40LDAuMQoJCQkJYzAuOSwxLjEsMiwxLjYsMy4yLDEuNnMyLjQtMC42LDMuMi0xLjZjMC40LTAuNCwxLTAuNSwxLjQtMC4xYzAuNCwwLjQsMC41LDEsMC4xLDEuNEMxMzEuNSwzNy43LDEyOS44LDM4LjUsMTI4LDM4LjV6Ii8+CgkJPC9nPgoJCTxnIG9wYWNpdHk9IjAuMiI+CgkJCTxjaXJjbGUgZmlsbD0iIzYxNjU2OCIgY3g9IjEyMSIgY3k9IjMyIiByPSIyLjUiLz4KCQk8L2c+CgkJPGc+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0xMjUuNSwyOWMtMC42LDAtMS0wLjQtMS0xYzAtMS4xLTAuOS0yLTItMnMtMiwwLjktMiwyYzAsMC42LTAuNCwxLTEsMXMtMS0wLjQtMS0xYzAtMi4yLDEuOC00LDQtNAoJCQkJczQsMS44LDQsNEMxMjYuNSwyOC42LDEyNi4xLDI5LDEyNS41LDI5eiIvPgoJCTwvZz4KCQk8Zz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTEzNi41LDI5Yy0wLjYsMC0xLTAuNC0xLTFjMC0xLjEtMC45LTItMi0ycy0yLDAuOS0yLDJjMCwwLjYtMC40LDEtMSwxcy0xLTAuNC0xLTFjMC0yLjIsMS44LTQsNC00CgkJCQlzNCwxLjgsNCw0QzEzNy41LDI4LjYsMTM3LjEsMjksMTM2LjUsMjl6Ii8+CgkJPC9nPgoJCTxnIG9wYWNpdHk9IjAuMiI+CgkJCTxjaXJjbGUgZmlsbD0iIzYxNjU2OCIgY3g9IjEzNSIgY3k9IjMyIiByPSIyLjUiLz4KCQk8L2c+CgkJPGcgb3BhY2l0eT0iMC4yIj4KCQkJPGNpcmNsZSBmaWxsPSIjNjE2NTY4IiBjeD0iMzY3IiBjeT0iMzIzLjQiIHI9IjQiLz4KCQk8L2c+CgkJPGcgb3BhY2l0eT0iMC4yIj4KCQkJPGNpcmNsZSBmaWxsPSIjNjE2NTY4IiBjeD0iMzk0LjEiIGN5PSIzMTYuMiIgcj0iNCIvPgoJCTwvZz4KCQk8Zz4KCQkJCgkJCQk8ZWxsaXBzZSB0cmFuc2Zvcm09Im1hdHJpeCgwLjk2NTkgLTAuMjU4OCAwLjI1ODggMC45NjU5IC02Ni4yNTAxIDExMC40NjI4KSIgZmlsbD0iIzYxNjU2OCIgY3g9IjM4Ni40IiBjeT0iMzA2LjgiIHJ4PSI0IiByeT0iNiIvPgoJCTwvZz4KCQk8Zz4KCQkJCgkJCQk8ZWxsaXBzZSB0cmFuc2Zvcm09Im1hdHJpeCgwLjk2NTkgLTAuMjU4OCAwLjI1ODggMC45NjU5IC02OC4wNDgzIDEwNi4xMjE2KSIgZmlsbD0iIzYxNjU2OCIgY3g9IjM2OSIgY3k9IjMxMS41IiByeD0iNCIgcnk9IjYiLz4KCQk8L2c+CgkJPGc+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0zNzksMzM5Yy0xMSwwLTIxLjItNy40LTI0LjItMTguNWwwLDBjLTMuNi0xMy4zLDQuNC0yNy4xLDE3LjctMzAuNmMxMy4zLTMuNiwyNy4xLDQuNCwzMC42LDE3LjcKCQkJCWMzLjYsMTMuMy00LjQsMjcuMS0xNy43LDMwLjZDMzgzLjMsMzM4LjcsMzgxLjEsMzM5LDM3OSwzMzl6IE0zNTYuOCwzMjBjMy4zLDEyLjIsMTUuOSwxOS41LDI4LjIsMTYuMwoJCQkJYzEyLjItMy4zLDE5LjUtMTUuOSwxNi4zLTI4LjJzLTE1LjktMTkuNS0yOC4yLTE2LjNDMzYwLjgsMjk1LjEsMzUzLjUsMzA3LjcsMzU2LjgsMzIwTDM1Ni44LDMyMHoiLz4KCQk8L2c+CgkJPGc+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0zNzkuOCwzMjkuOWMtMi41LDAtNC45LTAuNy03LjItMi4xYy0wLjUtMC4zLTAuNi0wLjktMC4zLTEuNGMwLjMtMC41LDAuOS0wLjYsMS40LTAuMwoJCQkJYzIuOCwxLjcsNS45LDIuMiw4LjksMS40YzMtMC44LDUuNS0yLjgsNy01LjdjMC4zLTAuNSwwLjktMC43LDEuNC0wLjRjMC41LDAuMywwLjcsMC45LDAuNCwxLjRjLTEuOCwzLjQtNC43LDUuNy04LjMsNi43CgkJCQlDMzgyLDMyOS44LDM4MC45LDMyOS45LDM3OS44LDMyOS45eiIvPgoJCTwvZz4KCQk8ZyBvcGFjaXR5PSIwLjUiPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNTA3LDEzNUgzODdjLTAuNiwwLTEtMC40LTEtMXMwLjQtMSwxLTFoMTIwYzAuNiwwLDEsMC40LDEsMVM1MDcuNiwxMzUsNTA3LDEzNXoiLz4KCQk8L2c+CgkJPGcgb3BhY2l0eT0iMC41Ij4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTI3MywyMzNIMTUzYy0wLjYsMC0xLTAuNC0xLTFzMC40LTEsMS0xaDEyMGMwLjYsMCwxLDAuNCwxLDFTMjczLjYsMjMzLDI3MywyMzN6Ii8+CgkJPC9nPgoJCTxnIG9wYWNpdHk9IjAuNSI+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0xMTAsMjU1Yy0wLjYsMC0xLTAuNC0xLTF2LTcyYzAtMC42LDAuNC0xLDEtMXMxLDAuNCwxLDF2NzJDMTExLDI1NC42LDExMC42LDI1NSwxMTAsMjU1eiIvPgoJCTwvZz4KCQk8ZyBvcGFjaXR5PSIwLjUiPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNzEuNCw5Mi40bC0xMy45LTEuMmMtMS43LTAuMS0zLjEsMS4xLTMuMywyLjdsLTEuMywxNC41Yy0wLjEsMC45LDEsMS40LDEuNiwwLjlsNC0zLjQKCQkJCWMwLjQtMC4zLDAuOS0wLjUsMS41LTAuNWwxMC4xLDAuOWMxLjcsMC4xLDMuMS0xLjEsMy4zLTIuN2wwLjctOEM3NC4yLDk0LDczLDkyLjUsNzEuNCw5Mi40eiIvPgoJCTwvZz4KCQk8Zz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTU2OC43LDg4LjhjLTAuNywwLTEuNC0wLjItMS45LTAuN2MtMC42LTAuNS0xLTEuMi0xLjEtMmMtMC4xLTEuNiwxLjEtMy4xLDIuNy0zLjIKCQkJCWMxLjctMC4xLDMuMSwxLjEsMy4zLDIuN2MwLjEsMC44LTAuMiwxLjYtMC43LDIuMnMtMS4yLDEtMiwxLjFDNTY4LjksODguOCw1NjguOCw4OC44LDU2OC43LDg4Ljh6IE01NjguNyw4NC44CgkJCQlDNTY4LjcsODQuOCw1NjguNiw4NC44LDU2OC43LDg0LjhjLTAuNiwwLjEtMSwwLjUtMSwxLjFjMCwwLjMsMC4xLDAuNSwwLjQsMC43czAuNSwwLjMsMC43LDAuMmwwLDBjMC4zLDAsMC41LTAuMSwwLjctMC40CgkJCQljMC4yLTAuMiwwLjMtMC41LDAuMi0wLjdDNTY5LjcsODUuMiw1NjkuMiw4NC44LDU2OC43LDg0Ljh6Ii8+CgkJPC9nPgoJCTxnIG9wYWNpdHk9IjAuMiI+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0zNzMuMyw2MC44TDM3My4zLDYwLjhjLTIuNC0wLjYtMy44LTMuMS0zLjItNS41bDMuOC0xNGw4LjcsMi4zbC0zLjgsMTRDMzc4LjIsNjAsMzc1LjcsNjEuNSwzNzMuMyw2MC44CgkJCQl6Ii8+CgkJPC9nPgoJCTxnPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMjY1LjcsMzE5Yy0wLjYsMC0xLjItMC4yLTEuNy0wLjVjLTAuNy0wLjUtMS4xLTEuMS0xLjItMS45bDAsMGMtMC4zLTEuNiwwLjgtMy4yLDIuNC0zLjUKCQkJCWMxLjYtMC4zLDMuMiwwLjgsMy41LDIuNGMwLjMsMS42LTAuOCwzLjItMi40LDMuNUMyNjYsMzE5LDI2NS44LDMxOSwyNjUuNywzMTl6IE0yNjQuNywzMTYuMmMwLDAuMywwLjIsMC41LDAuNCwwLjYKCQkJCWMwLjIsMC4yLDAuNSwwLjIsMC43LDAuMmMwLjUtMC4xLDAuOS0wLjYsMC44LTEuMmMtMC4xLTAuNS0wLjYtMC45LTEuMi0wLjhDMjY0LjksMzE1LjEsMjY0LjYsMzE1LjYsMjY0LjcsMzE2LjJMMjY0LjcsMzE2LjJ6IgoJCQkJLz4KCQk8L2c+CgkJPGc+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik01Ny43LDI0Mi44Yy0wLjYsMC0xLjItMC4yLTEuNy0wLjVjLTAuNy0wLjUtMS4xLTEuMS0xLjItMS45Yy0wLjMtMS42LDAuOC0zLjIsMi40LTMuNQoJCQkJYzAuOC0wLjEsMS42LDAsMi4yLDAuNWMwLjcsMC41LDEuMSwxLjEsMS4yLDEuOWMwLjMsMS42LTAuOCwzLjItMi40LDMuNUM1OCwyNDIuOCw1Ny45LDI0Mi44LDU3LjcsMjQyLjh6IE01Ny43LDIzOC44CgkJCQljLTAuMSwwLTAuMSwwLTAuMiwwYy0wLjUsMC4xLTAuOSwwLjYtMC44LDEuMmMwLDAuMywwLjIsMC41LDAuNCwwLjZjMC4yLDAuMiwwLjUsMC4yLDAuNywwLjJjMC4zLDAsMC41LTAuMiwwLjYtMC40CgkJCQljMC4yLTAuMiwwLjItMC41LDAuMi0wLjdjMC0wLjMtMC4yLTAuNS0wLjQtMC42QzU4LjEsMjM4LjgsNTcuOSwyMzguOCw1Ny43LDIzOC44eiIvPgoJCTwvZz4KCQk8ZyBvcGFjaXR5PSIwLjIiPgoJCQkKCQkJCTxyZWN0IHg9IjM5IiB5PSIyMDEuMSIgdHJhbnNmb3JtPSJtYXRyaXgoMC45ODQ4IC0wLjE3MzYgMC4xNzM2IDAuOTg0OCAtMzcuMTM4MiAxMi42OTA2KSIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjMwIiBoZWlnaHQ9IjM1Ii8+CgkJPC9nPgoJCTxnPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMzIzLjcsMjc1LjZjLTAuNCwwLTAuOC0wLjEtMS4xLTAuNGMtMC42LTAuNC0wLjktMS4xLTAuNy0xLjhsMS01LjZsLTQuMS00Yy0wLjUtMC41LTAuNy0xLjItMC41LTEuOQoJCQkJYzAuMi0wLjcsMC44LTEuMiwxLjUtMS4zbDUuNy0wLjhsMi41LTUuMWMwLjMtMC42LDEtMSwxLjctMWMwLjcsMCwxLjQsMC40LDEuNywxbDIuNSw1LjFsNS43LDAuOGMwLjcsMC4xLDEuMywwLjYsMS41LDEuMwoJCQkJczAsMS40LTAuNSwxLjlsLTQuMSw0bDEsNS42YzAuMSwwLjctMC4yLDEuNC0wLjcsMS44Yy0wLjYsMC40LTEuMywwLjUtMiwwLjFsLTUuMS0yLjdsLTUuMSwyLjcKCQkJCUMzMjQuMywyNzUuNSwzMjQsMjc1LjYsMzIzLjcsMjc1LjZ6IE0zMjAuMywyNjIuNWw0LDMuOWMwLjQsMC40LDAuNiwxLDAuNSwxLjdsLTAuOSw1LjRsNC45LTIuNmMwLjUtMC4zLDEuMi0wLjMsMS43LDBsNC45LDIuNgoJCQkJbC0wLjktNS40Yy0wLjEtMC42LDAuMS0xLjIsMC41LTEuN2w0LTMuOWwtNS41LTAuOGMtMC42LTAuMS0xLjEtMC41LTEuNC0xbC0yLjQtNWwtMi40LDVjLTAuMywwLjYtMC44LDAuOS0xLjQsMUwzMjAuMywyNjIuNXoKCQkJCSBNMzI5LjYsMjcyLjdDMzI5LjYsMjcyLjcsMzI5LjYsMjcyLjcsMzI5LjYsMjcyLjdMMzI5LjYsMjcyLjdDMzI5LjYsMjcyLjcsMzI5LjYsMjcyLjcsMzI5LjYsMjcyLjd6Ii8+CgkJPC9nPgoJCTxnPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNDE4LjEsMTA1LjZjLTAuMywwLTAuNS0wLjEtMC44LTAuMmwtNC0yLjFsLTQsMi4xYy0wLjYsMC4zLTEuMywwLjMtMS44LTAuMWMtMC41LTAuNC0wLjgtMS0wLjctMS43CgkJCQlsMC44LTQuNGwtMy4yLTMuMWMtMC41LTAuNS0wLjYtMS4xLTAuNC0xLjdzMC43LTEuMSwxLjQtMS4ybDQuNC0wLjZsMi00YzAuMy0wLjYsMC45LTAuOSwxLjUtMC45aDBjMC43LDAsMS4yLDAuNCwxLjUsMC45bDIsNAoJCQkJbDQuNCwwLjZjMC42LDAuMSwxLjIsMC41LDEuNCwxLjJjMC4yLDAuNiwwLDEuMy0wLjQsMS43bC0zLjIsMy4xbDAuOCw0LjRjMC4xLDAuNi0wLjEsMS4zLTAuNywxLjcKCQkJCUM0MTguOCwxMDUuNSw0MTguNSwxMDUuNiw0MTguMSwxMDUuNnogTTQwNi4zLDk1LjFsMi45LDIuOGMwLjQsMC40LDAuNiwxLDAuNSwxLjVsLTAuNyw0bDMuNi0xLjljMC41LTAuMywxLjEtMC4zLDEuNiwwbDMuNiwxLjkKCQkJCWwtMC43LTRjLTAuMS0wLjUsMC4xLTEuMSwwLjUtMS41bDIuOS0yLjhsLTQtMC42Yy0wLjYtMC4xLTEtMC40LTEuMy0wLjlsLTEuOC0zLjZsLTEuOCwzLjZjLTAuMiwwLjUtMC43LDAuOC0xLjMsMC45TDQwNi4zLDk1LjEKCQkJCXogTTQxMy41LDEwMy4yQzQxMy41LDEwMy4yLDQxMy41LDEwMy4yLDQxMy41LDEwMy4yTDQxMy41LDEwMy4yQzQxMy41LDEwMy4yLDQxMy41LDEwMy4yLDQxMy41LDEwMy4yeiIvPgoJCTwvZz4KCQk8Zz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTU5MywyNDB2MXY1djguNWMtMC43LTAuMy0xLjYtMC41LTIuNS0wLjVjLTIuNSwwLTQuNSwxLjMtNC41LDNzMiwzLDQuNSwzczQuNS0xLjMsNC41LTN2LTExLjVsMTMtMy4xdjgKCQkJCWMtMC43LTAuMy0xLjYtMC41LTIuNS0wLjVjLTIuNSwwLTQuNSwxLjMtNC41LDNzMiwzLDQuNSwzczQuNS0xLjMsNC41LTN2LTExdi0zdi0zTDU5MywyNDB6Ii8+CgkJPC9nPgoJCTxnPgoJCQk8Y2lyY2xlIGZpbGw9IiM2MTY1NjgiIGN4PSI4MCIgY3k9Ijg1LjEiIHI9IjYiLz4KCQk8L2c+CgkJPGc+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik00NjksMzQwLjljLTAuMywwLTAuNSwwLTAuOC0wLjFjLTAuOC0wLjItMS40LTAuNy0xLjgtMS40bC04LTEzLjlsMCwwYy0yLjUtNC40LTMuMi05LjUtMS45LTE0LjQKCQkJCXM0LjUtOSw4LjktMTEuNWM5LjEtNS4yLDIwLjctMi4xLDI2LDdjMi41LDQuNCwzLjIsOS41LDEuOSwxNC40Yy0xLjMsNC45LTQuNSw5LTguOSwxMS41bC0xMy45LDgKCQkJCUM0NzAsMzQwLjcsNDY5LjUsMzQwLjksNDY5LDM0MC45eiBNNDYwLjEsMzI0LjVsOCwxMy45YzAuMSwwLjIsMC4zLDAuNCwwLjYsMC41YzAuMywwLjEsMC41LDAsMC44LTAuMWwxMy45LTgKCQkJCWMzLjktMi4zLDYuNy01LjksNy45LTEwLjNjMS4yLTQuNCwwLjYtOS0xLjctMTIuOWMtNC43LTguMS0xNS4xLTEwLjktMjMuMi02LjJDNDU4LjIsMzA2LDQ1NS40LDMxNi40LDQ2MC4xLDMyNC41TDQ2MC4xLDMyNC41eiIKCQkJCS8+CgkJPC9nPgoJCTxnPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNDc0LjksMzIzYy0yLjQsMC00LjgtMS4zLTYuMS0zLjVsMCwwYy0xLjktMy4zLTAuOC03LjYsMi42LTkuNmMxLjYtMC45LDMuNS0xLjIsNS4zLTAuNwoJCQkJYzEuOCwwLjUsMy4zLDEuNiw0LjMsMy4zYzAuOSwxLjYsMS4yLDMuNSwwLjcsNS4zYy0wLjUsMS44LTEuNiwzLjMtMy4zLDQuMkM0NzcuMywzMjIuNyw0NzYuMSwzMjMsNDc0LjksMzIzeiBNNDcwLjUsMzE4LjUKCQkJCWMwLjcsMS4yLDEuNywyLDMsMi4zYzEuMywwLjMsMi42LDAuMiwzLjgtMC41YzEuMi0wLjcsMi0xLjcsMi4zLTNzMC4yLTIuNi0wLjUtMy44Yy0xLjQtMi40LTQuNC0zLjItNi44LTEuOAoJCQkJQzQ3MCwzMTMuMSw0NjkuMSwzMTYuMSw0NzAuNSwzMTguNUw0NzAuNSwzMTguNXoiLz4KCQk8L2c+CgkJPGc+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0xMTQuMSwyODguNWwtMi4xLTMuN2MtMC4zLTAuNS0wLjctMC44LTEuMi0wLjlsLTYuNC0xLjdsMy40LTcuOGMwLjUtMS4xLDAuNS0yLjMtMC4xLTMuMwoJCQkJcy0xLjQtMS44LTIuNi0yLjFsLTAuNi0wLjJjLTAuMiwwLTAuMy0wLjEtMC41LTAuMWMtMC43LDAtMS40LDAuNC0xLjcsMWwtMS45LDMuNGwtNi41LDYuOGwtMC42LDAuMWwwLjItMC43CgkJCQljMC4xLTAuNS0wLjItMS4xLTAuNy0xLjJsLTEyLjYtMy40Yy0wLjMtMC4xLTAuNSwwLTAuOCwwLjFjLTAuMiwwLjEtMC40LDAuNC0wLjUsMC42bC01LjQsMjAuM2MtMC4xLDAuMywwLDAuNSwwLjEsMC44CgkJCQljMC4xLDAuMiwwLjQsMC40LDAuNiwwLjVsMTIuNiwzLjRjMC4xLDAsMC4yLDAsMC4zLDBjMC40LDAsMC44LTAuMywxLTAuN2wwLjMtMS4xbDEuMSwxLjljMC4zLDAuNSwwLjcsMC44LDEuMiwwLjlsMTIuNiwzLjQKCQkJCWMwLjIsMCwwLjMsMC4xLDAuNSwwLjFjMC4zLDAsMC43LTAuMSwxLTAuM2wzLjctMi4xYzAuNC0wLjIsMC42LTAuNSwwLjgtMC45bDUtMTEuMUMxMTQuNSwyODkuOCwxMTQuNSwyODkuMSwxMTQuMSwyODguNXoKCQkJCSBNODYuMywyOTguMWwtMTAuNi0yLjhsNC45LTE4LjRsMTAuNiwyLjhsLTIuMyw4LjRsLTEuOSw3YzAsMCwwLDAsMCwwTDg2LjMsMjk4LjF6IE0xMDcuNCwzMDAuNmwtMy43LDIuMWwtMTIuNi0zLjRsLTIuMS0zLjcKCQkJCWwzLjYtMTMuNWwyLjItMC40bDcuMi03LjRsMi0zLjZsMC42LDAuMmMxLjIsMC4zLDEuOCwxLjYsMS4zLDIuN2wtMy40LDcuOGMtMC41LDEuMSwwLjEsMi40LDEuMywyLjdsNi40LDEuN2wyLjEsMy43CgkJCQlMMTA3LjQsMzAwLjZ6Ii8+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik04NC4yLDI5Mi4zYy0wLjgtMC4yLTEuNiwwLjMtMS44LDEuMWMtMC4yLDAuOCwwLjMsMS42LDEuMSwxLjhjMC44LDAuMiwxLjYtMC4zLDEuOC0xLjEKCQkJCUM4NS41LDI5My40LDg1LDI5Mi41LDg0LjIsMjkyLjN6Ii8+CgkJPC9nPgoJCTxnPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMTYyLDI1MXY1aDV2NGgtNXY1aC00di01aC01di00aDV2LTVIMTYyIE0xNjIsMjQ5aC00Yy0xLjEsMC0yLDAuOS0yLDJ2M2gtM2MtMS4xLDAtMiwwLjktMiwydjQKCQkJCWMwLDEuMSwwLjksMiwyLDJoM3YzYzAsMS4xLDAuOSwyLDIsMmg0YzEuMSwwLDItMC45LDItMnYtM2gzYzEuMSwwLDItMC45LDItMnYtNGMwLTEuMS0wLjktMi0yLTJoLTN2LTMKCQkJCUMxNjQsMjQ5LjksMTYzLjEsMjQ5LDE2MiwyNDlMMTYyLDI0OXoiLz4KCQk8L2c+CgkJPGc+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik01ODAuMiwxOTNjLTEuMywwLTIuNS0wLjMtMy43LTFjLTIuMi0xLjMtMy42LTMuNS0zLjYtNlYxNjBjMC0yLjUsMS4zLTQuNywzLjYtNgoJCQkJYzIuMy0xLjMsNS4yLTEuMyw3LjUsMC4xbDIxLjUsMTNjMi4xLDEuMywzLjQsMy41LDMuNCw1LjlzLTEuMyw0LjYtMy40LDUuOWwtMjEuNSwxM0M1ODIuOSwxOTIuNiw1ODEuNiwxOTMsNTgwLjIsMTkzegoJCQkJIE01ODAuMiwxNTVjLTAuOSwwLTEuOCwwLjItMi43LDAuN2MtMS42LDAuOS0yLjYsMi41LTIuNiw0LjNWMTg2YzAsMS44LDEsMy40LDIuNiw0LjNjMS43LDEsMy44LDAuOSw1LjUtMC4xbDIxLjUtMTMKCQkJCWMxLjUtMC45LDIuNC0yLjUsMi40LTQuMnMtMC45LTMuMy0yLjQtNC4ybC0yMS41LTEzQzU4Mi4yLDE1NS4zLDU4MS4yLDE1NSw1ODAuMiwxNTV6Ii8+CgkJPC9nPgoJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik00NTMuNiwyNjEuOGMtMC4xLTAuMi0wLjQtMC40LTAuNi0wLjVsLTguNy0yLjNjLTAuMy0wLjEtMC41LDAtMC44LDAuMXMtMC40LDAuNC0wLjUsMC42bDAsMC4ybC0wLjMtMC41CgkJCWwtMS41LTUuM2wtMC40LTIuMWMtMC4yLTAuNy0wLjctMS4zLTEuNC0xLjVsLTAuNy0wLjJjLTAuMy0wLjEtMC41LTAuMS0wLjgtMC4xYy0xLjYsMC0zLDEuMy0zLDNsLTAuMSw0LjRsLTMuMy0wLjkKCQkJYy0wLjIsMC0wLjMtMC4xLTAuNS0wLjFjLTAuMywwLTAuNywwLjEtMSwwLjNsLTIuNCwxLjRjLTAuNSwwLjMtMC45LDAuOS0xLDEuNWwtMC44LDdjLTAuMSwwLjQsMCwwLjksMC4zLDEuMmwxLjQsMi40CgkJCWMwLjMsMC41LDAuNywwLjgsMS4yLDAuOWw4LjcsMi4zYzAuMiwwLDAuMywwLjEsMC41LDAuMWMwLjMsMCwwLjctMC4xLDEtMC4zbDAuNy0wLjRsLTAuMywxLjFjLTAuMSwwLjUsMC4yLDEuMSwwLjcsMS4ybDguNywyLjMKCQkJYzAuMSwwLDAuMiwwLDAuMywwYzAuNCwwLDAuOC0wLjMsMS0wLjdsMy45LTE0LjVDNDUzLjgsMjYyLjMsNDUzLjgsMjYyLDQ1My42LDI2MS44eiBNNDM3LjgsMjcxLjdsLTguNy0yLjNsLTEuNC0yLjRsMC44LTcKCQkJbDIuNC0xLjRsNC42LDEuMmMwLjEsMCwwLjIsMCwwLjMsMGMwLjUsMCwxLTAuNCwxLTFsMC4xLTUuN2MwLTAuNiwwLjUtMSwxLTFjMC4xLDAsMC4yLDAsMC4zLDBsMC43LDAuMmwwLjQsMi4ybDEuNiw1LjZsMS40LDIuNAoJCQlsLTIuMSw3LjdMNDM3LjgsMjcxLjd6IE00NDguMiwyNzUuNWwtNi44LTEuOGwyLjYtOS44bDAuMi0wLjhjMCwwLDAsMCwwLDBsMC41LTEuOWw2LjgsMS44TDQ0OC4yLDI3NS41eiIvPgoJCTxnIG9wYWNpdHk9IjAuNSI+CgkJCTxnPgoJCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTQ1Mi45LDI3NS43Yy0wLjEsMC0wLjIsMC0wLjMsMGMtMC41LTAuMS0wLjgtMC43LTAuNy0xLjJsMy40LTEyLjZjMC4xLTAuNS0wLjItMS4xLTAuNy0xLjJsLTQuNS0xLjIKCQkJCQljLTAuNS0wLjEtMC44LTAuNy0wLjctMS4yczAuNy0wLjgsMS4yLTAuN2w0LjUsMS4yYzEuNiwwLjQsMi41LDIuMSwyLjEsMy43bC0zLjQsMTIuNkM0NTMuNywyNzUuNSw0NTMuMywyNzUuNyw0NTIuOSwyNzUuN3oiLz4KCQkJPC9nPgoJCTwvZz4KCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNzcuNCwyMzYuM2wtNi45LTM5LjRjLTAuMi0xLjMtMS0yLjUtMi4xLTMuMmMtMS4xLTAuOC0yLjQtMS4xLTMuNy0wLjhsLTI5LjUsNS4yYy0xLjMsMC4yLTIuNSwxLTMuMiwyLjEKCQkJYy0wLjgsMS4xLTEuMSwyLjQtMC44LDMuN2w2LjksMzkuNGMwLjIsMS4zLDEsMi41LDIuMSwzLjJjMC45LDAuNiwxLjgsMC45LDIuOSwwLjljMC4zLDAsMC42LDAsMC45LTAuMWwxOC43LTMuM2wxLjQsNy45CgkJCWMwLjEsMC40LDAuMywwLjYsMC43LDAuOGMwLjEsMCwwLjIsMC4xLDAuMywwLjFjMC4yLDAsMC41LTAuMSwwLjctMC4ybDMuOS0zLjRsNC45LDEuOWMwLjMsMC4xLDAuNywwLjEsMS0wLjIKCQkJYzAuMy0wLjIsMC40LTAuNiwwLjMtMC45bC0xLjQtOGMwLjktMC40LDEuNy0xLDIuMy0xLjhDNzcuMywyMzguOSw3Ny42LDIzNy42LDc3LjQsMjM2LjN6IE02OS42LDI0Ni45Yy0wLjMtMC4xLTAuNy0wLjEtMSwwLjIKCQkJbC0zLjEsMi43bC0yLjUtMTRsNy45LTEuNGwyLjUsMTRMNjkuNiwyNDYuOXogTTQzLDIzNy4zbC01LjctMzIuNWwyNy42LTQuOWw1LjcsMzIuNUw0MywyMzcuM3ogTTc0LjksMjM4LjkKCQkJYy0wLjMsMC40LTAuNiwwLjctMSwwLjlsLTEuMi02LjdsLTYuMS0zNC41YzAtMC4zLTAuMi0wLjUtMC40LTAuNmMtMC4yLTAuMi0wLjUtMC4yLTAuNy0wLjJMMzYsMjAzYy0wLjUsMC4xLTAuOSwwLjYtMC44LDEuMgoJCQlsNi4xLDM0LjVjMC4xLDAuNSwwLjUsMC44LDEsMC44YzAuMSwwLDAuMSwwLDAuMiwwbDE4LjctMy4zbDEsNS45bC0xOC43LDMuM2MtMC44LDAuMS0xLjYsMC0yLjItMC41Yy0wLjctMC41LTEuMS0xLjEtMS4yLTEuOQoJCQlMMzMsMjAzLjVjLTAuMS0wLjgsMC0xLjYsMC41LTIuMmMwLjUtMC43LDEuMS0xLjEsMS45LTEuMmwyOS41LTUuMmMwLjIsMCwwLjQsMCwwLjUsMGMwLjYsMCwxLjIsMC4yLDEuNywwLjUKCQkJYzAuNywwLjUsMS4xLDEuMSwxLjIsMS45bDYuOSwzOS40Qzc1LjYsMjM3LjQsNzUuNCwyMzguMiw3NC45LDIzOC45eiIvPgoJCTxnPgoJCQkKCQkJCTxlbGxpcHNlIHRyYW5zZm9ybT0ibWF0cml4KDAuOTk2MiAtOC43MTU1NzRlLTAyIDguNzE1NTc0ZS0wMiAwLjk5NjIgLTAuNDkzMyA1MC40NDQ5KSIgZmlsbD0iIzYxNjU2OCIgY3g9IjU3Ny40IiBjeT0iMzAuOSIgcng9IjIuNSIgcnk9IjQiLz4KCQk8L2c+CgkJPGc+CgkJCQoJCQkJPGVsbGlwc2UgdHJhbnNmb3JtPSJtYXRyaXgoMC45OTYyIC04LjcxNTU3NGUtMDIgOC43MTU1NzRlLTAyIDAuOTk2MiAtMC4zNjggNTEuMzk2MykiIGZpbGw9IiM2MTY1NjgiIGN4PSI1ODguNCIgY3k9IjI5LjkiIHJ4PSIyLjUiIHJ5PSI0Ii8+CgkJPC9nPgoJCTxnPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNTgzLjQsNDQuNGMtMi4zLDAtNC41LTEtNi4zLTIuOGMtMC40LTAuNC0wLjQtMSwwLTEuNGMwLjQtMC40LDEtMC40LDEuNCwwYzEuNiwxLjYsMy41LDIuMyw1LjQsMi4yCgkJCQljMi0wLjIsMy43LTEuMyw1LTMuMWMwLjMtMC41LDAuOS0wLjYsMS40LTAuM2MwLjUsMC4zLDAuNiwwLjksMC4zLDEuNGMtMS42LDIuMy0zLjksMy43LTYuNSwzLjkKCQkJCUM1ODMuOSw0NC40LDU4My43LDQ0LjQsNTgzLjQsNDQuNHoiLz4KCQk8L2c+CgkJPGcgb3BhY2l0eT0iMC4yIj4KCQkJPGNpcmNsZSBmaWxsPSIjNjE2NTY4IiBjeD0iNTkyLjQiIGN5PSIzNS42IiByPSIzIi8+CgkJPC9nPgoJCTxnIG9wYWNpdHk9IjAuMiI+CgkJCTxjaXJjbGUgZmlsbD0iIzYxNjU2OCIgY3g9IjU3NC41IiBjeT0iMzcuMiIgcj0iMyIvPgoJCTwvZz4KCQk8Zz4KCQkJPGc+CgkJCQk8cmVjdCB4PSI0MjIiIHk9IjQzIiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMzYiIGhlaWdodD0iMSIvPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuNzUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDI0IiB5PSIzMiIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMTAiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDI0IiB5PSIyNSIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMiIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuNSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0MjQiIHk9IjIyIiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSIxIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC41Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQyNyIgeT0iMjciIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjEiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDMwIiB5PSIyOSIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMSIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuNSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0MzMiIHk9IjIxIiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSIxIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC41Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQzNiIgeT0iMjYiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjEiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDM5IiB5PSIyMCIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMSIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuNSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0NDIiIHk9IjI0IiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSIxIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC41Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQ0NSIgeT0iMzMiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjEiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDQ4IiB5PSIyOSIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMSIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuNSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0NTEiIHk9IjIyIiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSIxIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC41Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQ1NCIgeT0iMjgiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjEiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjM1Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQyNCIgeT0iMjgiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjMiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjc1Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQyNyIgeT0iMzkiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjMiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDI3IiB5PSIzMSIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMiIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuMzUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDI3IiB5PSIzNSIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMyIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuNzUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDMwIiB5PSIzOSIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMyIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuNSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0MzAiIHk9IjMyIiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSIyIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC4zNSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0MzAiIHk9IjM1IiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSIzIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC43NSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0MzMiIHk9IjMyIiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSIxMCIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuNSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0MzMiIHk9IjI0IiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSIzIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC4zNSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0MzMiIHk9IjI4IiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSIzIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC43NSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0MzYiIHk9IjM2IiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSI2Ii8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC41Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQzNiIgeT0iMjkiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjIiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjM1Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQzNiIgeT0iMzIiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjMiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjc1Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQzOSIgeT0iMzAiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjEyIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC41Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQzOSIgeT0iMjMiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjIiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjM1Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQzOSIgeT0iMjYiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjMiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjc1Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQ0MiIgeT0iMzQiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjgiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDQyIiB5PSIyNyIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMiIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuMzUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDQyIiB5PSIzMCIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMyIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuNzUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDQ1IiB5PSI0MSIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMSIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuNSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0NDUiIHk9IjM2IiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSIxIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC4zNSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0NDUiIHk9IjM4IiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSIyIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC43NSI+CgkJCQk8Zz4KCQkJCQk8cmVjdCB4PSI0NDgiIHk9IjM5IiBmaWxsPSIjNjE2NTY4IiB3aWR0aD0iMiIgaGVpZ2h0PSIzIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC41Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQ0OCIgeT0iMzIiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjIiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjM1Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQ0OCIgeT0iMzUiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjMiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjc1Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQ1MSIgeT0iMzIiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjEwIi8+CgkJCQk8L2c+CgkJCTwvZz4KCQkJPGcgb3BhY2l0eT0iMC41Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQ1MSIgeT0iMjUiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjIiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjM1Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQ1MSIgeT0iMjgiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjMiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjc1Ij4KCQkJCTxnPgoJCQkJCTxyZWN0IHg9IjQ1NCIgeT0iMzgiIGZpbGw9IiM2MTY1NjgiIHdpZHRoPSIyIiBoZWlnaHQ9IjQiLz4KCQkJCTwvZz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDU0IiB5PSIzMSIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMiIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJCTxnIG9wYWNpdHk9IjAuMzUiPgoJCQkJPGc+CgkJCQkJPHJlY3QgeD0iNDU0IiB5PSIzNCIgZmlsbD0iIzYxNjU2OCIgd2lkdGg9IjIiIGhlaWdodD0iMyIvPgoJCQkJPC9nPgoJCQk8L2c+CgkJPC9nPgoJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik01NTQuNywyMjMuNGwtMTIuMi01LjJjLTAuMy0wLjEtMC41LTAuNC0wLjYtMC43bC0yLjYtMTNjLTAuMi0xLjEtMS4xLTItMi4yLTIuM2MtMS4xLTAuMy0yLjMsMC4xLTMsMC45CgkJCWwtNy4yLDguMlYxNDZjMC01LTQtOS05LTlIMTM0LjhjLTAuOS01LjgtNS44LTEwLjEtMTEuOC0xMC4xYy0zLjMsMC02LjYsMS40LTksMy43Yy0yLjQtMi4zLTUuNy0zLjctOS0zLjdjLTYuNywwLTEyLDUuMy0xMiwxMgoJCQljMCw4LDYuOSwxNC4zLDE3LjQsMjMuOGwyLjYsMi4zdjc1LjdjMCwxLjYsMC45LDMuMSwyLjUsMy43YzAuNSwwLjIsMSwwLjMsMS42LDAuM2MxLDAsMi0wLjQsMi44LTEuMmwxMy4xLTEzLjEKCQkJYzAuOS0wLjksMi4yLTEuNSwzLjUtMS41aDM3OC42bC01LjQsMTEuNmMtMC41LDEtMC4zLDIuMiwwLjQsMy4xYzAuNywwLjksMS45LDEuMywzLDFsMTIuOS0yLjljMC4zLTAuMSwwLjcsMCwwLjksMC4ybDkuNyw5CgkJCWMwLjYsMC41LDEuMywwLjgsMiwwLjhjMC40LDAsMC43LTAuMSwxLjEtMC4yYzEuMS0wLjQsMS44LTEuNCwxLjktMi41bDEuMi0xMy4yYzAtMC4zLDAuMi0wLjYsMC41LTAuOGwxMS42LTYuNQoJCQljMS0wLjYsMS42LTEuNiwxLjUtMi44QzU1Ni41LDIyNC44LDU1NS44LDIyMy44LDU1NC43LDIyMy40eiBNOTUsMTM4LjljMC01LjYsNC40LTEwLDEwLTEwYzMuMSwwLDYuMiwxLjQsOC4yLDMuOAoJCQljMC40LDAuNCwxLjEsMC40LDEuNSwwYzItMi40LDUuMS0zLjgsOC4yLTMuOGM1LjYsMCwxMCw0LjQsMTAsMTBjMCw3LjEtNi42LDEzLjEtMTYuNywyMi4zbC0yLjMsMi4xbC0yLjMtMi4xCgkJCUMxMDEuNywxNTIsOTUsMTQ2LDk1LDEzOC45eiBNMTMxLjUsMjI5LjFsLTEzLjEsMTMuMWMtMC42LDAuNi0xLjQsMC44LTIuMiwwLjRjLTAuOC0wLjMtMS4yLTEtMS4yLTEuOFYxNjVsMi42LTIuNAoJCQljMTAuNC05LjQsMTcuMy0xNS43LDE3LjMtMjMuNmgzODNjMy45LDAsNywzLjEsNyw3djY3LjNjLTAuMSwwLjEtMC4zLDAuMS0wLjUsMC4xbC0xMy4yLTEuNmMtMS4xLTAuMS0yLjIsMC40LTIuOSwxLjMKCQkJYy0wLjYsMS0wLjcsMi4yLTAuMSwzLjJsNi40LDEwLjdIMTM2LjVDMTM0LjYsMjI3LDEzMi45LDIyNy43LDEzMS41LDIyOS4xeiBNNTU0LDIyN2wtMTEuNiw2LjVjLTAuOSwwLjUtMS40LDEuNC0xLjUsMi4zCgkJCWwtMS4yLDEzLjJjMCwwLjQtMC4zLDAuNy0wLjYsMC44Yy0wLjQsMC4xLTAuOCwwLjEtMS0wLjJsLTkuNy05Yy0wLjYtMC41LTEuMy0wLjgtMi0wLjhjLTAuMiwwLTAuNCwwLTAuNywwLjFjMCwwLDAsMCwwLDAKCQkJbC0xMi45LDIuOWMtMC40LDAuMS0wLjgsMC0xLTAuM2MtMC4yLTAuMy0wLjMtMC43LTAuMS0xbDUuNS0xMmMwLjQtMC45LDAuNC0xLjktMC4xLTIuOGwtNi44LTExLjRjLTAuMi0wLjMtMC4yLTAuNywwLTEuMQoJCQljMC4yLTAuMywwLjYtMC41LDEtMC40bDEzLjIsMS42YzEsMC4xLDItMC4zLDIuNi0xbDguNy0xMGMwLjMtMC4zLDAuNi0wLjQsMS0wLjNjMC40LDAuMSwwLjYsMC40LDAuNywwLjhsMi42LDEzCgkJCWMwLjIsMSwwLjgsMS44LDEuOCwyLjJsMTIuMiw1LjJjMC40LDAuMiwwLjYsMC41LDAuNiwwLjlTNTU0LjMsMjI2LjgsNTU0LDIyN3oiLz4KCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMjE2LDI3MGMtOS40LDAtMTcsNy42LTE3LDE3czcuNiwxNywxNywxN3MxNy03LjYsMTctMTdTMjI1LjQsMjcwLDIxNiwyNzB6IE0yMjUuNywyODYKCQkJYy0wLjEtMS44LTAuMy0zLjUtMC42LTUuMWMzLjEsMS4yLDUuMiwzLDUuOCw1LjFIMjI1Ljd6IE0yMjMuNywyODZIMjE3di02LjdjMi4xLDAuMSw0LjEsMC40LDUuOCwwLjkKCQkJQzIyMy4zLDI4MS45LDIyMy42LDI4My45LDIyMy43LDI4NnogTTIxNywyNzcuM3YtNS4yYzIsMC41LDMuOSwyLjcsNS4xLDUuOEMyMjAuNSwyNzcuNiwyMTguOCwyNzcuNCwyMTcsMjc3LjN6IE0yMTUsMjcyLjF2NS4yCgkJCWMtMS44LDAuMS0zLjUsMC4zLTUuMSwwLjZDMjExLjEsMjc0LjgsMjEzLDI3Mi43LDIxNSwyNzIuMXogTTIxNSwyNzkuM3Y2LjdoLTYuN2MwLjEtMi4xLDAuNC00LjEsMC45LTUuOAoJCQlDMjEwLjksMjc5LjcsMjEyLjksMjc5LjQsMjE1LDI3OS4zeiBNMjA2LjMsMjg2aC01LjJjMC41LTIsMi43LTMuOSw1LjgtNS4xQzIwNi42LDI4Mi41LDIwNi40LDI4NC4yLDIwNi4zLDI4NnogTTIwNi4zLDI4OAoJCQljMC4xLDEuOCwwLjMsMy41LDAuNiw1LjFjLTMuMS0xLjItNS4yLTMtNS44LTUuMUgyMDYuM3ogTTIwOC4zLDI4OGg2Ljd2Ni43Yy0yLjEtMC4xLTQuMS0wLjQtNS44LTAuOQoJCQlDMjA4LjcsMjkyLjEsMjA4LjQsMjkwLjEsMjA4LjMsMjg4eiBNMjE1LDI5Ni43djUuMmMtMi0wLjUtMy45LTIuNy01LjEtNS44QzIxMS41LDI5Ni40LDIxMy4yLDI5Ni42LDIxNSwyOTYuN3ogTTIxNywzMDEuOXYtNS4yCgkJCWMxLjgtMC4xLDMuNS0wLjMsNS4xLTAuNkMyMjAuOSwyOTkuMiwyMTksMzAxLjMsMjE3LDMwMS45eiBNMjE3LDI5NC43VjI4OGg2LjdjLTAuMSwyLjEtMC40LDQuMS0wLjksNS44CgkJCUMyMjEuMSwyOTQuMywyMTkuMSwyOTQuNiwyMTcsMjk0Ljd6IE0yMjUuNywyODhoNS4yYy0wLjUsMi0yLjcsMy45LTUuOCw1LjFDMjI1LjQsMjkxLjUsMjI1LjYsMjg5LjgsMjI1LjcsMjg4eiBNMjI5LjksMjgxLjMKCQkJYy0xLjQtMS4xLTMuMy0yLjEtNS40LTIuOGMtMC43LTIuMi0xLjYtNC0yLjgtNS40QzIyNS40LDI3NC42LDIyOC40LDI3Ny42LDIyOS45LDI4MS4zeiBNMjEwLjMsMjczLjFjLTEuMSwxLjQtMi4xLDMuMy0yLjgsNS40CgkJCWMtMi4yLDAuNy00LDEuNi01LjQsMi44QzIwMy42LDI3Ny42LDIwNi42LDI3NC42LDIxMC4zLDI3My4xeiBNMjAyLjEsMjkyLjdjMS40LDEuMSwzLjMsMi4xLDUuNCwyLjhjMC43LDIuMiwxLjYsNCwyLjgsNS40CgkJCUMyMDYuNiwyOTkuNCwyMDMuNiwyOTYuNCwyMDIuMSwyOTIuN3ogTTIyMS43LDMwMC45YzEuMS0xLjQsMi4xLTMuMywyLjgtNS40YzIuMi0wLjcsNC0xLjYsNS40LTIuOAoJCQlDMjI4LjQsMjk2LjQsMjI1LjQsMjk5LjQsMjIxLjcsMzAwLjl6Ii8+CgkJPGc+CgkJCTxnPgoJCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTMzMy41LDc4YzYuMywwLDExLjUsNS4yLDExLjUsMTEuNXMtNS4yLDExLjUtMTEuNSwxMS41UzMyMiw5NS44LDMyMiw4OS41UzMyNy4yLDc4LDMzMy41LDc4IE0zMzMuNSw3NgoJCQkJCUMzMjYsNzYsMzIwLDgyLDMyMCw4OS41czYsMTMuNSwxMy41LDEzLjVTMzQ3LDk3LDM0Nyw4OS41UzM0MSw3NiwzMzMuNSw3NkwzMzMuNSw3NnoiLz4KCQkJPC9nPgoJCQk8ZyBvcGFjaXR5PSIwLjUiPgoJCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTM1NywxMjUuMmMtMC44LDAtMS41LTAuMy0yLjEtMC45bC03LjYtNy42Yy0wLjQtMC40LTAuNC0xLDAtMS40czEtMC40LDEuNCwwbDcuNiw3LjYKCQkJCQljMC40LDAuNCwxLDAuNCwxLjQsMGwzLjYtMy42YzAuNC0wLjQsMS0wLjQsMS40LDBzMC40LDEsMCwxLjRsLTMuNiwzLjZDMzU4LjUsMTI0LjksMzU3LjgsMTI1LjIsMzU3LDEyNS4yeiIvPgoJCQk8L2c+CgkJPC9nPgoJCTxnPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMjE2LDg1aC0zNmMtMS43LDAtMy0xLjMtMy0zVjQ2YzAtMS43LDEuMy0zLDMtM2gzNmMxLjcsMCwzLDEuMywzLDN2MzZDMjE5LDgzLjcsMjE3LjcsODUsMjE2LDg1egoJCQkJIE0xODAsNDVjLTAuNiwwLTEsMC40LTEsMXYzNmMwLDAuNiwwLjQsMSwxLDFoMzZjMC42LDAsMS0wLjQsMS0xVjQ2YzAtMC42LTAuNC0xLTEtMUgxODB6Ii8+CgkJPC9nPgoJCTxnIG9wYWNpdHk9IjAuNSI+CgkJCTxnPgoJCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTIxOCw4OWgtMzRjLTAuNiwwLTEtMC40LTEtMXMwLjQtMSwxLTFoMzRjMS43LDAsMy0xLjMsMy0zdi04YzAtMC42LDAuNC0xLDEtMXMxLDAuNCwxLDF2OAoJCQkJCUMyMjMsODYuOCwyMjAuOCw4OSwyMTgsODl6Ii8+CgkJCTwvZz4KCQk8L2c+CgkJPGc+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0zNzMuOCw2MS45Yy0wLjEsMC0wLjIsMC0wLjMsMGwtMS0wLjNjMCwwLDAsMCwwLDBsLTE4LjMtNC45Yy0xLjMtMC4zLTIuNC0xLjItMy0yLjNzLTAuOC0yLjUtMC41LTMuOAoJCQkJbDYuMi0yMy4yYzAsMCwwLDAsMCwwYzAuNC0xLjYsMi4xLTIuNSwzLjctMi4xbDE0LjUsMy45YzAuOCwwLjIsMS40LDAuNywxLjgsMS40YzAuNCwwLjcsMC41LDEuNSwwLjMsMi4zTDM3MSw1NgoJCQkJYy0wLjIsMC44LTAuMSwxLjYsMC4zLDIuM2MwLjQsMC43LDEsMS4yLDEuOCwxLjRsMSwwLjNjMC41LDAuMSwwLjgsMC43LDAuNywxLjJDMzc0LjYsNjEuNywzNzQuMiw2MS45LDM3My44LDYxLjl6IE0zNTguOCwyNy45CgkJCQlsLTYuMiwyMy4yYy0wLjIsMC44LTAuMSwxLjYsMC4zLDIuM2MwLjQsMC43LDEsMS4yLDEuOCwxLjRsMTQuNSwzLjljLTAuNC0xLTAuNS0yLjEtMC4yLTMuMmw2LjItMjMuMmMwLjEtMC4zLDAtMC41LTAuMS0wLjgKCQkJCWMtMC4xLTAuMi0wLjMtMC40LTAuNi0wLjVMMzYwLDI3LjJDMzU5LjUsMjcuMSwzNTksMjcuNCwzNTguOCwyNy45TDM1OC44LDI3Ljl6Ii8+CgkJPC9nPgoJCTxnIG9wYWNpdHk9IjAuNSI+CgkJCTxnPgoJCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTM1MSwzNy45Yy0wLjEsMC0wLjIsMC0wLjMsMGMtMC41LTAuMS0wLjgtMC43LTAuNy0xLjJsMy4zLTEyLjNjMC43LTIuNywzLjUtNC4yLDYuMS0zLjVsNS44LDEuNQoJCQkJCWMwLjUsMC4xLDAuOCwwLjcsMC43LDEuMmMtMC4xLDAuNS0wLjcsMC45LTEuMiwwLjdsLTUuOC0xLjVjLTEuNi0wLjQtMy4yLDAuNS0zLjcsMi4xTDM1MiwzNy4yQzM1MS45LDM3LjYsMzUxLjUsMzcuOSwzNTEsMzcuOQoJCQkJCXoiLz4KCQkJPC9nPgoJCTwvZz4KCQk8Zz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTM3NS4xLDYyLjFjLTAuNSwwLTEtMC4xLTEuNi0wLjJsMC41LTEuOWMxLDAuMywyLjEsMC4xLDMtMC40YzAuOS0wLjUsMS42LTEuNCwxLjktMi40bDMuNC0xMi42CgkJCQljMC4xLTAuMywwLTAuNS0wLjEtMC44Yy0wLjEtMC4yLTAuMy0wLjQtMC42LTAuNWwtNy43LTIuMWwwLjUtMS45bDcuNywyLjFjMC44LDAuMiwxLjQsMC43LDEuOCwxLjRjMC40LDAuNywwLjUsMS41LDAuMywyLjMKCQkJCWwtMy40LDEyLjZjLTAuNCwxLjUtMS40LDIuOC0yLjgsMy42QzM3Ny4yLDYxLjgsMzc2LjEsNjIuMSwzNzUuMSw2Mi4xeiIvPgoJCTwvZz4KCQk8Zz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTE3OS43LDgzLjdsLTEuNC0xLjRsMTctMTdjMC40LTAuNCwxLTAuNCwxLjQsMGw3LjMsNy4zbDUuMy01LjNjMC40LTAuNCwxLTAuNCwxLjQsMGw4LDhsLTEuNCwxLjQKCQkJCWwtNy4zLTcuM2wtNS4zLDUuM2MtMC40LDAuNC0xLDAuNC0xLjQsMGwtNy4zLTcuM0wxNzkuNyw4My43eiIvPgoJCTwvZz4KCQk8Zz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTIwOCw3OWMtMC4zLDAtMC41LTAuMS0wLjctMC4zbC00LTRjLTAuNC0wLjQtMC40LTEsMC0xLjRzMS0wLjQsMS40LDBsNCw0YzAuNCwwLjQsMC40LDEsMCwxLjQKCQkJCUMyMDguNSw3OC45LDIwOC4zLDc5LDIwOCw3OXoiLz4KCQk8L2c+CgkJPGcgb3BhY2l0eT0iMC41Ij4KCQkJPGc+CgkJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMTg2LDU3TDE4Niw1N2MwLDIuOCwyLjIsNSw1LDVsMCwwYzIuOCwwLDUtMi4yLDUtNXYwYzAtMi44LTIuMi01LTUtNWwwLDBDMTg4LjIsNTIsMTg2LDU0LjIsMTg2LDU3eiIKCQkJCQkvPgoJCQk8L2c+CgkJPC9nPgoJCTxnIG9wYWNpdHk9IjAuNSI+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik03Ni43LDIxMS4zYy0wLjUsMC0wLjktMC4zLTEtMC44TDczLDE5NS4yYy0wLjMtMS42LTEuMi0zLTIuNS0zLjljLTEuMy0wLjktMi45LTEuMy00LjUtMWwtMjIuNCw0CgkJCQljLTAuNSwwLjEtMS4xLTAuMy0xLjItMC44czAuMy0xLjEsMC44LTEuMmwyMi40LTRjMi4xLTAuNCw0LjIsMC4xLDYsMS4zczIuOSwzLjEsMy4zLDUuMmwyLjcsMTUuM2MwLjEsMC41LTAuMywxLjEtMC44LDEuMgoJCQkJQzc2LjgsMjExLjMsNzYuNywyMTEuMyw3Ni43LDIxMS4zeiIvPgoJCTwvZz4KCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNjEuOCwzMDkuMmMtMC4xLTEuMy0wLjctMi41LTEuOC0zLjRjLTEtMC45LTIuMy0xLjMtMy42LTEuMmwtMTkuOSwxLjdjMCwwLDAsMCwwLDAKCQkJYy0yLjcsMC4yLTQuOCwyLjctNC41LDUuNGwwLjMsNGwtNywwLjZjLTIuNywwLjItNC44LDIuNy00LjUsNS40bDEuNiwxOC41YzAuMSwwLjgsMC42LDEuNSwxLjQsMS43YzAuMiwwLjEsMC40LDAuMSwwLjYsMC4xCgkJCWMwLjYsMCwxLjEtMC4zLDEuNS0wLjdsMy40LTRjMC4yLTAuMiwwLjQtMC4zLDAuNy0wLjRsMTcuMS0xLjVjMi43LTAuMiw0LjgtMi43LDQuNS01LjRsLTAuMy00bDQuMi0wLjRjMC4zLDAsMC41LDAuMSwwLjcsMC4yCgkJCWw0LDMuNGMwLjQsMC4zLDAuOCwwLjUsMS4zLDAuNWMwLjMsMCwwLjYtMC4xLDAuOS0wLjJjMC43LTAuNCwxLjEtMS4xLDEuMS0xLjlMNjEuOCwzMDkuMnogTTQ5LjYsMzMwLjRjMC4xLDEuNi0xLjEsMy4xLTIuNywzLjIKCQkJbC0xNy4xLDEuNWMtMC44LDAuMS0xLjUsMC41LTIsMS4xbC0zLjQsNGwtMS42LTE4LjVjLTAuMS0xLjYsMS4xLTMuMSwyLjctMy4zbDctMC42bDAuNCw1YzAuMSwxLjMsMC43LDIuNSwxLjgsMy40CgkJCWMxLDAuOSwyLjMsMS4zLDMuNiwxLjJsMTEtMUw0OS42LDMzMC40eiBNNTcuNSwzMjQuNWMtMC41LTAuNS0xLjItMC43LTEuOS0wLjdjLTAuMSwwLTAuMiwwLTAuMywwbC0xNy4xLDEuNQoJCQljLTAuOCwwLjEtMS42LTAuMi0yLjItMC43Yy0wLjYtMC41LTEtMS4yLTEuMS0ybC0xLTExYy0wLjEtMS42LDEuMS0zLjEsMi43LTMuM2wxOS45LTEuN2MwLjgtMC4xLDEuNiwwLjIsMi4yLDAuNwoJCQljMC42LDAuNSwxLDEuMiwxLjEsMmwxLjYsMTguNUw1Ny41LDMyNC41eiIvPgoJCTxnPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMjc5LjcsMzAwLjljMC44LDAuNiwxLjgsMC45LDIuOSwwLjljMC4zLDAsMC42LDAsMC45LTAuMWMxLjMtMC4yLDIuNS0xLDMuMi0yLjEKCQkJCWMwLjgtMS4xLDEuMS0yLjQsMC44LTMuN2MtMC4yLTEuMy0xLTIuNS0yLjEtMy4yYy0xLjEtMC44LTIuNC0xLjEtMy43LTAuOGMtMS4zLDAuMi0yLjUsMS0zLjIsMi4xCgkJCQlDMjc2LjksMjk2LjIsMjc3LjUsMjk5LjMsMjc5LjcsMzAwLjl6IE0yODAuMSwyOTUuMWMwLjUtMC43LDEuMS0xLjEsMS45LTEuMmMwLjIsMCwwLjQsMCwwLjUsMGMwLjYsMCwxLjIsMC4yLDEuNywwLjUKCQkJCWMwLjcsMC41LDEuMSwxLjEsMS4yLDEuOXMwLDEuNi0wLjUsMi4yYy0wLjUsMC43LTEuMSwxLjEtMS45LDEuMmMtMC44LDAuMS0xLjYsMC0yLjItMC41YzAsMCwwLDAsMCwwCgkJCQlDMjc5LjUsMjk4LjMsMjc5LjIsMjk2LjQsMjgwLjEsMjk1LjF6Ii8+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik0zMDcuNCwzMTYuOGwtMy0xNi43Yy0wLjItMS4zLTEtMi41LTIuMS0zLjJjLTEuMS0wLjgtMi40LTEuMS0zLjctMC44bC0zLjEsMC42Yy0wLjEtNC0yLTcuOS01LjUtMTAuNAoJCQkJYy01LjktNC4xLTE0LTIuNy0xOC4xLDMuMmMtMi41LDMuNS0yLjksNy45LTEuNiwxMS43bC03LjEsMS4yYy0xLjMsMC4yLTIuNSwxLTMuMiwyLjFjLTAuOCwxLjEtMS4xLDIuNC0wLjgsMy43bDMsMTYuNwoJCQkJYzAuNCwyLjQsMi41LDQuMSw0LjksNC4xYzAuMywwLDAuNiwwLDAuOS0wLjFsMzUuNS02LjNDMzA2LjEsMzIyLjEsMzA3LjksMzE5LjUsMzA3LjQsMzE2Ljh6IE0yNzMuOSwzMDYuNAoJCQkJYzAuNCwwLjMsMC44LDAuNywxLjIsMWw4LjcsNi4xYzAuNCwwLjMsMC45LDAuNCwxLjMsMC40YzAuNywwLDEuNS0wLjMsMS45LTFsNi4xLTguN2MwLjMtMC40LDAuNi0wLjksMC44LTEuNGwzLjctMC43bDIuNiwxNC44CgkJCQlsLTI4LjYsNWwtMi42LTE0LjhMMjczLjksMzA2LjR6IE0yNzMuNiwyOTAuNWMzLjUtNSwxMC40LTYuMiwxNS4zLTIuN2M1LDMuNSw2LjIsMTAuNCwyLjcsMTUuM2wtNi4xLDguNwoJCQkJYy0wLjEsMC4yLTAuMywwLjItMC41LDAuMWwtOC43LTYuMUMyNzEuMywzMDIuMywyNzAuMSwyOTUuNCwyNzMuNiwyOTAuNXogTTMwMywzMjAuNmwtMzUuNSw2LjNjLTEuNiwwLjMtMy4yLTAuOC0zLjUtMi40CgkJCQlsLTMtMTYuN2MtMC4xLTAuOCwwLTEuNiwwLjUtMi4yYzAuNS0wLjcsMS4xLTEuMSwxLjktMS4ybDcuNS0xLjNjMC4zLDAuNiwwLjcsMS4yLDEuMiwxLjhsLTQuNCwwLjhjLTAuMywwLTAuNSwwLjItMC42LDAuNAoJCQkJYy0wLjIsMC4yLTAuMiwwLjUtMC4yLDAuN2wzLDE2LjdjMCwwLjMsMC4yLDAuNSwwLjQsMC42YzAuMiwwLjEsMC40LDAuMiwwLjYsMC4yYzAuMSwwLDAuMSwwLDAuMiwwbDMwLjUtNS40CgkJCQljMC41LTAuMSwwLjktMC42LDAuOC0xLjJsLTMtMTYuN2MtMC4xLTAuNS0wLjYtMC45LTEuMi0wLjhsLTMuNCwwLjZjMC4yLTAuNywwLjQtMS40LDAuNS0yLjFsMy42LTAuNmMwLjIsMCwwLjQsMCwwLjUsMAoJCQkJYzAuNiwwLDEuMiwwLjIsMS43LDAuNWMwLjcsMC41LDEuMSwxLjEsMS4yLDEuOWwzLDE2LjdDMzA1LjcsMzE4LjcsMzA0LjcsMzIwLjMsMzAzLDMyMC42eiIvPgoJCTwvZz4KCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNjE1LjgsMzM2LjVsLTMuNy0zLjdjLTEuNS0xLjUtMy41LTItNS40LTEuNmMwLjQtMS45LTAuMi0zLjktMS42LTUuNGwtMy43LTMuN2MtMS4xLTEuMS0yLjYtMS43LTQuMi0xLjcKCQkJcy0zLjEsMC42LTQuMiwxLjdjLTEuMSwxLjEtMS43LDIuNi0xLjcsNC4yczAuNiwzLjEsMS43LDQuMmwzLjcsMy43YzEuMiwxLjIsMi43LDEuNyw0LjIsMS43YzAuNCwwLDAuOCwwLDEuMi0wLjEKCQkJYy0wLjQsMS45LDAuMiwzLjksMS42LDUuNGwzLjcsMy43YzEuMSwxLjEsMi42LDEuNyw0LjIsMS43YzEuNiwwLDMuMS0wLjYsNC4yLTEuN3MxLjctMi42LDEuNy00LjIKCQkJQzYxNy42LDMzOS4xLDYxNi45LDMzNy42LDYxNS44LDMzNi41eiBNNTk2LjQsMzI3LjFjLTAuNC0wLjQtMC40LTEsMC0xLjRsMC4yLTAuMmMwLDAsMCwwLDAsMGMwLjItMC4yLDAuNC0wLjMsMC43LTAuMwoJCQljMC4zLDAsMC41LDAuMSwwLjcsMC4zbDEuNywxLjdjLTAuMywwLjItMC43LDAuNC0wLjksMC42Yy0wLjMsMC4zLTAuNSwwLjYtMC42LDAuOUw1OTYuNCwzMjcuMXogTTYwMC4xLDMzMC44CgkJCWMtMC4yLTAuMi0wLjMtMC41LTAuMy0wLjhzMC4xLTAuNiwwLjMtMC44YzAuMi0wLjIsMC41LTAuMywwLjgtMC4zczAuNiwwLjEsMC44LDAuM2w3LDdjMC4yLDAuMiwwLjMsMC41LDAuMywwLjgKCQkJcy0wLjEsMC42LTAuMywwLjhjLTAuNCwwLjQtMS4yLDAuNC0xLjYsMEw2MDAuMSwzMzAuOHogTTYxMC4yLDMzOS4zYzAuMy0wLjMsMC41LTAuNiwwLjYtMC45bDEuNywxLjdjMC40LDAuNCwwLjQsMSwwLDEuNAoJCQlsLTAuMiwwLjJjLTAuNCwwLjQtMSwwLjQtMS40LDBsLTEuNy0xLjdDNjA5LjUsMzM5LjgsNjA5LjksMzM5LjUsNjEwLjIsMzM5LjN6IE01OTQuNSwzMjkuMmMtMC43LTAuNy0xLjItMS43LTEuMi0yLjgKCQkJczAuNC0yLDEuMi0yLjhzMS43LTEuMiwyLjgtMS4yczIsMC40LDIuOCwxLjJsMy43LDMuN2MwLjYsMC42LDEsMS40LDEuMSwyLjNsLTEuNi0xLjZsLTAuMS0wLjFsLTMuOC0zLjhjLTEuMS0xLjEtMy4xLTEuMS00LjIsMAoJCQlsLTAuMiwwLjJjLTEuMiwxLjItMS4yLDMuMSwwLDQuMmwzLjgsMy44bDAuMSwwLjFsMS42LDEuNmMtMC44LTAuMS0xLjYtMC41LTIuMy0xLjFMNTk0LjUsMzI5LjJ6IE02MTQuNCwzNDMuNQoJCQljLTEuNSwxLjUtNC4xLDEuNS01LjYsMGwtMy43LTMuN2MtMC42LTAuNi0xLTEuNC0xLjEtMi4zbDEuNiwxLjZsMC4xLDAuMWwzLjgsMy44YzAuNiwwLjYsMS4zLDAuOSwyLjEsMC45YzAuOCwwLDEuNi0wLjMsMi4xLTAuOQoJCQlsMC4yLTAuMmMxLjItMS4yLDEuMi0zLjEsMC00LjJsLTMuOC0zLjhjMCwwLDAsMCwwLDBsLTEuNi0xLjZjMC44LDAuMSwxLjYsMC41LDIuMywxLjFsMy43LDMuN2MwLjcsMC43LDEuMiwxLjcsMS4yLDIuOAoJCQlTNjE1LjEsMzQyLjgsNjE0LjQsMzQzLjV6Ii8+CgkJPGc+CgkJCTxwYXRoIGZpbGw9IiM2MTY1NjgiIGQ9Ik00NzYuNiw4Ny43Yy0xLjUsMS4xLTIuNiwyLjctMi45LDQuNWwtMC41LDNjLTAuMSwwLjUsMC4zLDEuMSwwLjgsMS4ybDIzLjYsNC4yYzAuMSwwLDAuMSwwLDAuMiwwCgkJCQljMC41LDAsMC45LTAuMywxLTAuOGwwLjUtM2MwLjctMy44LTEuOS03LjQtNS43LTguMWwtMi4xLTAuNGMwLjUtMC40LDEuMS0wLjksMS42LTEuNWMxLjUtMS43LDIuNi00LDMtNS44CgkJCQljMC4zLTEuOC0wLjEtMy43LTEuMi01LjJjLTEuMS0xLjUtMi43LTIuNi00LjUtMi45Yy0zLjgtMC43LTcuNCwxLjktOC4xLDUuN2MtMC40LDIuMiwwLjIsNS45LDEuOCw4LjRsLTIuMi0wLjQKCQkJCUM0ODAsODYuMiw0NzguMiw4Ni42LDQ3Ni42LDg3Ljd6IE00OTcuNCw5Ni40bC0wLjMsMmwtMjEuNy0zLjhsMC4zLTJjMC4yLTEuMywxLTIuNSwyLjEtMy4yYzEuMS0wLjgsMi40LTEuMSwzLjctMC44bDUuOSwxCgkJCQljMCwwLDAsMCwwLDBjMCwwLDAsMCwwLDBsNS45LDFDNDk2LjEsOTEsNDk3LjksOTMuNiw0OTcuNCw5Ni40eiBNNDg0LjIsNzguOGMwLjQtMi40LDIuNS00LjEsNC45LTQuMWMwLjMsMCwwLjYsMCwwLjksMC4xCgkJCQljMS4zLDAuMiwyLjUsMSwzLjIsMi4xYzAuOCwxLjEsMS4xLDIuNCwwLjgsMy43YzAsMCwwLDAsMCwwYy0wLjUsMi45LTMuOCw3LjUtNi4zLDdsMCwwQzQ4NS4zLDg3LjEsNDgzLjcsODEuNyw0ODQuMiw3OC44eiIvPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNTA4LjcsNjYuOWMtMy4zLTAuNi02LjQsMS42LTcsNC45Yy0wLjYsMy4zLDEuNiw2LjQsNC45LDdzNi40LTEuNiw3LTQuOQoJCQkJQzUxNC4xLDcwLjYsNTEyLDY3LjQsNTA4LjcsNjYuOXoiLz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTUyMC40LDU3LjhjLTIuMi0wLjQtNC4zLDEuMS00LjYsMy4yYy0wLjQsMi4yLDEuMSw0LjMsMy4yLDQuNmMyLjIsMC40LDQuMy0xLjEsNC42LTMuMgoJCQkJUzUyMi42LDU4LjIsNTIwLjQsNTcuOHoiLz4KCQkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTUxNC4xLDQ3LjVjLTEuMS0wLjItMi4xLDAuNS0yLjMsMS42Yy0wLjIsMS4xLDAuNSwyLjEsMS42LDIuM2MxLjEsMC4yLDIuMS0wLjUsMi4zLTEuNgoJCQkJQzUxNS45LDQ4LjcsNTE1LjIsNDcuNyw1MTQuMSw0Ny41eiIvPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNTEwLjcsODEuMmMwLjUsMi43LDAuNiw1LjUsMC4xLDguM2MtMi4yLDEyLjUtMTQuMSwyMC45LTI2LjYsMTguN2MtMTIuNS0yLjItMjAuOS0xNC4yLTE4LjctMjYuNgoJCQkJYzEuMS02LjEsNC40LTExLjMsOS41LTE0LjhjMy45LTIuNyw4LjUtNC4yLDEzLjEtNC4yYzEuMywwLDIuNywwLjEsNCwwLjRjMy4zLDAuNiw2LjQsMS45LDksMy43YzAuNS0wLjUsMS0xLDEuNi0xLjMKCQkJCWMtMy0yLjEtNi40LTMuNi0xMC4yLTQuM2MtNi42LTEuMi0xMy4yLDAuMy0xOC43LDQuMWMtNS41LDMuOC05LjEsOS42LTEwLjMsMTYuMWMtMi40LDEzLjYsNi43LDI2LjYsMjAuMywyOQoJCQkJYzEuNSwwLjMsMi45LDAuNCw0LjQsMC40YzExLjksMCwyMi41LTguNSwyNC42LTIwLjdjMC42LTMuMywwLjUtNi41LTAuMi05LjZDNTEyLDgwLjcsNTExLjQsODEsNTEwLjcsODEuMnoiLz4KCQk8L2c+CgkJPHBhdGggb3BhY2l0eT0iMC4yIiBmaWxsPSIjNjE2NTY4IiBkPSJNNTcwLjgsNTUuOGMtMC42LDAuNy0xLjcsMC4zLTEuOC0wLjZsLTAuNC00LjZsLTEyLDFsMi43LDMwLjlsMTcuOS0xLjZsLTIuNi0yOS43CgkJCWMtMC4yLDAuMS0wLjQsMC4zLTAuNSwwLjRMNTcwLjgsNTUuOHoiLz4KCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNNTk5LjIsMjEuOWMtMC4yLTIuNy0yLjctNC44LTUuNC00LjVsLTIzLjksMi4xYy0xLjMsMC4xLTIuNSwwLjctMy40LDEuOGMtMC45LDEtMS4zLDIuMy0xLjIsMy42CgkJCWwxLjcsMTkuOWwtMTEsMWMtMS4zLDAuMS0yLjUsMC43LTMuNCwxLjhzLTEuMywyLjMtMS4yLDMuNmwzLjEsMzUuOWMwLjIsMi42LDIuNCw0LjYsNSw0LjZjMC4xLDAsMC4zLDAsMC40LDBsMTcuOS0xLjYKCQkJYzIuNy0wLjIsNC44LTIuNyw0LjUtNS40bC0yLjktMzIuOWwxNi45LTEuNWMyLjctMC4yLDQuOC0yLjcsNC41LTUuNEw1OTkuMiwyMS45eiBNNTczLjksNTMuN2wyLjMsMjYuNWwtMTUuOSwxLjRsLTIuNS0yOC45CgkJCWwxMC0wLjlsMC4zLDMuNmMwLjEsMC44LDAuNiwxLjUsMS40LDEuN2MwLjIsMC4xLDAuNCwwLjEsMC42LDAuMWMwLjYsMCwxLjEtMC4zLDEuNS0wLjdMNTczLjksNTMuN3ogTTU4MC43LDg0LjgKCQkJYzAuMSwxLjYtMS4xLDMuMS0yLjcsMy4zTDU2MCw4OS42Yy0xLjcsMC4xLTMuMS0xLjEtMy4yLTIuN0w1NTMuNiw1MWMtMC4xLTAuOCwwLjItMS42LDAuNy0yLjJjMC41LTAuNiwxLjItMSwyLTEuMWwxMS0xbDAuMywzCgkJCWwtMTEsMWMtMC4zLDAtMC41LDAuMS0wLjcsMC40Yy0wLjIsMC4yLTAuMywwLjUtMC4yLDAuN2wyLjcsMzAuOWMwLDAuNSwwLjUsMC45LDEsMC45YzAsMCwwLjEsMCwwLjEsMGwxNy45LTEuNgoJCQljMC4zLDAsMC41LTAuMSwwLjctMC40YzAuMi0wLjIsMC4zLTAuNSwwLjItMC43bC0yLjUtMjguOWwyLTAuMkw1ODAuNyw4NC44eiBNNTk2LjUsNDguM2wtMjEuMSwxLjhjLTAuOCwwLjEtMS41LDAuNC0yLDEuMQoJCQlsLTMuNCw0bC0yLjctMzAuNWMtMC4xLTAuOCwwLjItMS42LDAuNy0yLjJjMC41LTAuNiwxLjItMSwyLTEuMWwyMy45LTIuMWMxLjctMC4xLDMuMSwxLjEsMy4yLDIuN2wyLDIyLjkKCQkJQzU5OS40LDQ2LjcsNTk4LjIsNDguMSw1OTYuNSw0OC4zeiIvPgoJCTxnPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMjg1LjcsMTIxLjNsLTQuOS0xOC40YzAtMC4xLTAuMS0wLjItMC4yLTAuNGMtMC4xLTAuMS0wLjItMC4yLTAuMy0wLjNsLTQuNS0yLjZsLTAuOS0zLjUKCQkJCWMtMC4yLTAuOC0wLjctMS40LTEuNC0xLjhjLTAuNy0wLjQtMS41LTAuNS0yLjMtMC4zbC0zLjUsMC45bC00LTIuM2MtMS40LTAuOC0zLjMtMC4zLTQuMSwxLjFsLTIuMyw0bC0zLjUsMC45CgkJCQljLTAuOCwwLjItMS40LDAuNy0xLjgsMS40Yy0wLjQsMC43LTAuNSwxLjUtMC4zLDIuM2wwLjksMy41bC0yLjYsNC41YzAsMCwwLDAsMCwwYy0wLjEsMC4xLTAuMSwwLjItMC4xLDAuM2MwLDAsMCwwLDAsMAoJCQkJYzAsMC4xLDAsMC4zLDAsMC40bDQuOSwxOC40YzAuMSwwLjMsMC4yLDAuNSwwLjUsMC42YzAuMiwwLjEsMC4zLDAuMSwwLjUsMC4xYzAuMSwwLDAuMiwwLDAuMywwbDI5LTcuOAoJCQkJQzI4NS42LDEyMi40LDI4NS45LDEyMS44LDI4NS43LDEyMS4zeiBNMjc4LjUsMTAzLjZsLTEuMSwxLjlsLTAuOC0zLjFMMjc4LjUsMTAzLjZ6IE0yNjEuNCw5NC44YzAuMy0wLjUsMC45LTAuNiwxLjQtMC40CgkJCQlsMi4zLDEuM2wtNSwxLjNMMjYxLjQsOTQuOHogTTI1NC40LDEwMC43bDE3LjQtNC43YzAuMy0wLjEsMC41LDAsMC44LDAuMWMwLjIsMC4xLDAuNCwwLjMsMC41LDAuNmwzLDExLjJsLTUuMiw5LjFsLTUsMS4zCgkJCQlsLTkuMS01LjJsLTMtMTEuMkMyNTMuNSwxMDEuNCwyNTMuOCwxMDAuOSwyNTQuNCwxMDAuN3ogTTI1NC4yLDExMS43bC0xLjktMS4xbDEuMS0xLjlMMjU0LjIsMTExLjd6IE0yNTYuNSwxMjguMWwtNC0xNS4xCgkJCQlsMi44LDEuNmw5LjgsNS43YzAuMiwwLjEsMC4zLDAuMSwwLjUsMC4xYzAuMSwwLDAuMiwwLDAuMywwbDUuOC0xLjZjMC4zLTAuMSwwLjUtMC4yLDAuNi0wLjVsNS43LTkuOGwxLjYtMi44bDQsMTUuMQoJCQkJTDI1Ni41LDEyOC4xeiIvPgoJCQk8cGF0aCBmaWxsPSIjNjE2NTY4IiBkPSJNMjY1LjEsMTExLjFjMC40LDAsMC45LTAuMSwxLjMtMC4yYzIuNy0wLjcsNC4yLTMuNSwzLjUtNi4xYy0wLjctMi43LTMuNS00LjItNi4xLTMuNQoJCQkJYy0yLjcsMC43LTQuMiwzLjUtMy41LDYuMUMyNjAuOSwxMDkuNiwyNjIuOSwxMTEuMSwyNjUuMSwxMTEuMXogTTI2NC4zLDEwMy4yYzAuMy0wLjEsMC41LTAuMSwwLjgtMC4xYzEuMywwLDIuNSwwLjksMi45LDIuMgoJCQkJYzAuNCwxLjYtMC41LDMuMi0yLjEsMy43Yy0xLjYsMC40LTMuMi0wLjUtMy43LTIuMUMyNjEuOCwxMDUuMywyNjIuNywxMDMuNiwyNjQuMywxMDMuMnoiLz4KCQk8L2c+CgkJPHBhdGggZmlsbD0iIzYxNjU2OCIgZD0iTTM2My43LDExMi4zbC0xMS0xMWMtMC40LTAuNC0xLTAuNC0xLjQsMGwtMC44LDAuOGwtMi42LTIuNmMyLTIuOCwzLjEtNi4zLDMuMS0xMAoJCQljMC05LjctNy44LTE3LjUtMTcuNS0xNy41UzMxNiw3OS44LDMxNiw4OS41czcuOCwxNy41LDE3LjUsMTcuNWMzLjcsMCw3LjEtMS4yLDEwLTMuMWwyLjYsMi42bC0wLjgsMC44Yy0wLjQsMC40LTAuNCwxLDAsMS40CgkJCWwxMSwxMWMwLjIsMC4yLDAuNSwwLjMsMC43LDAuM3MwLjUtMC4xLDAuNy0wLjNsNi02QzM2NC4xLDExMy4zLDM2NC4xLDExMi43LDM2My43LDExMi4zeiBNMzE4LDg5LjVjMC04LjUsNy0xNS41LDE1LjUtMTUuNQoJCQljOC41LDAsMTUuNSw3LDE1LjUsMTUuNWMwLDguNS03LDE1LjUtMTUuNSwxNS41QzMyNSwxMDUsMzE4LDk4LDMxOCw4OS41eiBNMzQ1LDEwMi42YzAuNi0wLjUsMS4xLTEsMS42LTEuNmwyLjUsMi41bC0xLjYsMS42CgkJCUwzNDUsMTAyLjZ6IE0zNTcsMTE3LjZsLTkuNi05LjZsNC42LTQuNmw5LjYsOS42TDM1NywxMTcuNnoiLz4KCTwvZz4KPC9nPgo8ZyBpZD0iRWJlbmVfMiIgZGlzcGxheT0ibm9uZSI+CjwvZz4KPC9zdmc+Cg==","color":"#3766b8"}},"showPreview":0,"welcome_screen":"\/\/s3.eu-central-1.amazonaws.com\/qrcgappcdn\/social-media-solution\/welcome.png","sharing":true};

            //Upgrade old vcards created before 13.04 with show_directions parameter
            if (angular.isUndefined(json_data.show_directions))
                json_data.show_directions = true;

            previewService.pushData(json_data);

            function setAvatarBackgroundImage() {
                if ($scope.view.code) {
                    if ($scope.view.code.avatar)
                        return {
                            'background': 'url(' + $scope.view.code.avatar + ')'
                        };
                    else return {
                        'height': '0px',
                        'background': 'none'
                    }
                }
            }

            function getBackgroundColor() {
                if ($scope.view.code) {
                    var color1 = $scope.view.code.color1 || '#607d8b';
                    if (!$scope.view.code.show_gradient)
                        return {"background": color1};
                }
            }

            $scope.getBackgroundColor = getBackgroundColor;
            $scope.setAvatarBackgroundImage = setAvatarBackgroundImage;

            window.setTimeout(function () {

                $(".loading-vcard").fadeOut();
                $(".vcard-functions-wrapper a:visible:last").addClass("last-element");
            }, 500);

            /**
             * Copy short ulr to clipboard
             *
             * @param elem - input element with the link
             * */
            $scope.ifCopySucceed = false;
            $scope.copyLinkToClipboard = function (elem) {
                var targetId = "_hiddenCopyText_";
                var isInput = elem.tagName === "INPUT" || elem.tagName === "TEXTAREA";
                var origSelectionStart, origSelectionEnd;
                if (isInput) {
                    // can just use the original source element for the selection and copy
                    target = elem;
                    origSelectionStart = elem.selectionStart;
                    origSelectionEnd = elem.selectionEnd;
                } else {
                    // must use a temporary form element for the selection and copy
                    target = document.getElementById(targetId);
                    if (!target) {
                        var target = document.createElement("textarea");
                        target.style.position = "absolute";
                        target.style.left = "-9999px";
                        target.style.top = "0";
                        target.id = targetId;
                        document.body.appendChild(target);
                    }
                    target.textContent = elem.textContent;
                }
                // select the content
                var currentFocus = document.activeElement;
                target.focus();
                target.setSelectionRange(0, target.value.length);

                // copy the selection
                var succeed;
                try {
                    succeed = document.execCommand("copy");
                } catch (e) {
                    succeed = false;
                }
                // restore original focus
                if (currentFocus && typeof currentFocus.focus === "function") {
                    currentFocus.focus();
                }

                if (isInput) {
                    // restore prior selection
                    elem.setSelectionRange(origSelectionStart, origSelectionEnd);
                } else {
                    // clear temporary content
                    target.textContent = "";
                }
                $scope.$apply(function () {
                    $scope.ifCopySucceed = succeed;
                });
                setTimeout(function () {
                    $scope.$apply(function () {
                        $scope.ifCopySucceed = false;
                    });
                }, 1500)
            };

            /**
             * Set text color based on the background
             *
             * @param color - background color
             * */
            $scope.isColorLight = function (color) {
                var c;
                if (/^#([A-Fa-f0-9]{3}){1,2}$/.test(color)) {
                    c = color.substring(1).split('');
                    if (c.length == 3) {
                        c = [c[0], c[0], c[1], c[1], c[2], c[2]];
                    }
                    c = '0x' + c.join('');

                    var r = (c >> 16) & 255,
                        g = (c >> 8) & 255,
                        b = c & 255;
                    // Counting the perceptive luminance
                    // human eye favors green color...
                    var a = 1 - (0.240 * r + 0.470 * g + 0.150 * b) / 255;
                    return (a < 0.4);
                }
            };
            /**
             * Watch showPreview value
             *
             * @param p1 - new value
             * @param p2 - old value
             * */
            $scope.$watch("view.showPreview", function (p1, p2, p3) {
                if (p1 != undefined && p1 == 'infinite') {
                    setTimeout(function () {
                        $(".loading-welcome.welcome-screen").show();
                        $("#welcomeImg").fadeIn(1000);
                    }, 500)
                } else if (p1 == undefined && p2 != undefined && p2 == 'infinite') {
                    $("#welcomeImg").hide();
                    $(".loading-welcome").fadeOut();
                } else if ((p1 != undefined && p2 != undefined && p1 != p2) || (p1 != undefined && p1 != 0 && p2 == undefined && p1 != p2)) {
                    setTimeout(function () {
                        $(".loading-welcome.welcome-screen").show();
                        $("#welcomeImg").hide();
                        $("#welcomeImg").fadeIn(1000);
                        setTimeout(function () {
                            $(".loading-welcome").fadeOut();
                        }, 2000)
                    }, 500)
                }
            });

            $scope.setAvatar = function () {
                return {
                    'background': $scope.view.code.avatar ? 'url(' + $scope.view.code.avatar + ')' : 'none'
                }
            };

            /**
             * Set avatar background with extra options like zoom and background color
             * */
            $scope.setAvatarExtra = function () {
                var style = {};
                if ($scope.view.code) {
                    /*
                    * Apply custom header image and background color
                    * */
                    if ($scope.view.code.customHeaderImage && $scope.view.code.customHeaderImage.url) {
                        if ($scope.view.code.customHeaderImage.color != null) {
                            style = {
                                'background-color': $scope.view.code.customHeaderImage.color,
                                '-webkit-mask': 'url("' + $scope.view.code.customHeaderImage.url + '") no-repeat 50% 50%',
                                'mask': 'url("' + $scope.view.code.customHeaderImage.url + '") no-repeat 50% 50%',
                                '-webkit-mask-size': 'cover',
                                'mask-size':'cover'
                            };
                            $('.vcard-top-info.avatar-container').css('background-color', $scope.view.code.customHeaderImage.color);
                        } else
                            style = {
                                'background-image': 'url("' + $scope.view.code.customHeaderImage.url + '")',
                                'background-size': '100%'
                            }
                    }
                    else if ($scope.view.code.avatar)
                        style = {
                            'background': 'url("' + $scope.view.code.avatar + '")',
                            'background-size': '100%!important',
                            'background-color': '#ffffff'
                        };
                    else
                        style = {
                            'height': '0px',
                            'background': 'none'
                        };
                    if ($scope.view.code.avatar_extra) {
                        style['background-size'] = $scope.view.code.avatar_extra.zoom + '%';
                        if (!($scope.view.code.customHeaderImage && $scope.view.code.customHeaderImage.url && $scope.view.code.customHeaderImage.color != null)) {
                            style['background-color'] = $scope.view.code.avatar_extra.background;
                        }
                    }
                }
                // Convert array to string to avoid problems with vendor prefixes.
                var string_style = '';
                angular.forEach(style, function (value, key) {
                    string_style += key + ': ' + value + ';';
                });
                // Bad solution, but works (Alex).
                $('.vcard-top-info.avatar-container').attr('style', string_style);
                return {};
            };

            /**
             * Watch avatarExtra values and set the css
             * */
            $scope.$watch('view.code.avatar_extra', function (newVal) {
                if (newVal) {
                    $('.avatar-container').css({
                        'background-size': newVal.zoom + '%!important',
                        'background-color': newVal.background,
                        'background-position': 'center center'
                    });
                }
            });

            $(document).ready(function () {
                /**
                 * To work, function 'copyLinkToClipboard' needs to be called from an event listener on the copy button
                 * */
                document.getElementById("copyButton").addEventListener("click", function () {
                    $scope.copyLinkToClipboard(document.getElementById("shortUrl"));
                });
            })

        }
    );

    if (parent && typeof parent.ImHere === "function") {
        parent.ImHere();
    } else {
        //Only load this on standalone pages not inframe working
        SocialShareKit.init();
    }

    /**
     * Toggle fab
     *
     * @param id - id of the fab
     */
    function toggleFab(id) {

        $(id + ' .prime').toggleClass('is-active');
        $(id + ' #prime').toggleClass('is-float');
        $($(id).parent()).toggleClass('fabOnTop');
        $('#prime.fab').toggleClass('disabledClick');
        $(id + ' .fixed-blur-bgd').toggle();
        $(id + ' .chat').toggleClass('is-visible');

    }

    $(document).ready(function () {

        /**
         * On window resize if width is bigger then tablet remove calendar and share mobile style
         * */
        $(window).resize(function () {
            if (window.innerWidth >= 667) {
                $('.follow-scroll.calendar-container').removeAttr('style');
                $('.follow-scroll.share-container').removeAttr('style');
            }
        });

        /**
         * Close fab from close icon
         * */
        $('#prime, .icon-fab-close').click(function () {
            var id = $($(this).closest('.fabs')).attr('id');
            toggleFab('#' + id);
        });

        /**
         * Close fab on blur bgd click
         * */
        $('.fixed-blur-bgd').click(function () {
            if (event.target == $(this)[0]) {
                $($("#prime.is-float").parent().parent()).removeClass('fabOnTop');
                $('.prime').removeClass('is-active');
                $('#prime').removeClass('is-float');
                $('#prime.fab').removeClass('disabledClick');
                $('.chat, .dialog-container').removeClass('is-visible');
                $(this).hide();
            }
        });


        /**
         * Ripple effect on element
         */
        var ink, d, x, y;
        $(".ripplelink").click(function (e) {
            if ($(this).find(".ink").length === 0) {
                $(this).prepend("<span class='ink'></span>");
            }

            ink = $(this).find(".ink");
            ink.removeClass("animate");

            if (!ink.height() && !ink.width()) {
                d = Math.max($(this).outerWidth(), $(this).outerHeight());
                ink.css({height: d, width: d});
            }

            x = e.pageX - $(this).offset().left - ink.width() / 2;
            y = e.pageY - $(this).offset().top - ink.height() / 2;

            ink.css({top: y + 'px', left: x + 'px'}).addClass("animate");
        });
    });

/*]]>*/
</script>
</body>

</body>
</html>
