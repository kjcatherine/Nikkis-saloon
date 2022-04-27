(function($) {
    "use strict";
    jQuery(document).ready(function($) {
        // Back To Top Button
        jQuery( window ).scroll( function () {
            if ( jQuery( this ).scrollTop() > 100 ) {
                jQuery( '.back-to-top' ).fadeIn();
            } else {
                jQuery( '.back-to-top' ).fadeOut();
            }
        } );
        jQuery( '.back-to-top' ).on('click', function () {
            jQuery( "html, body" ).animate( { scrollTop: 0 }, 1500, 'easeInOutExpo' );
            return false;
        } );
        
        // Initilize Superfish Menu
        $("ul.main-menu").superfish({
            delay:          300,
            hoverClass:     'sfHover',
            animation:     {opacity: "show"},   
            speed:          200,
            speedOut:       0,
            cssArrows:      true
        });

        /* Open Submenu on left side when Screen is too small */
        var wapoMainWindowWidth;
        var subMenuExist;
        var subMenuWidth;
        var newSubMenuPosition;

        function sfSubmenuPosition() {
            wapoMainWindowWidth = $(window).width();
            $('#navigation ul li ul').mouseover(function(){     
                subMenuExist = $(this).find('.sub-menu').length;            
                if( subMenuExist > 0){
                    subMenuWidth = $(this).find('.sub-menu').width();
                    newSubMenuPosition = subMenuWidth + 3;
                    $(this).find('.sub-menu').css({
                        left: -newSubMenuPosition,
                        top: '0',
                    });
                }
             });
        }
        sfSubmenuPosition();
    
        // Footer Columns
        $('.multi-col-widget').isotope({
          itemSelector: '.widget',
          layoutMode: 'masonry' // masonry or fitRows
        });

        // Before & After Slider
        $('.cocoen').cocoen();

        // Video Popup
        $('.video-link').magnificPopup({
            type: 'iframe',
            mainClass: 'mfp-fade',
            preloader: true,
        });

        // Galley Popup
         $('.gallery-item').magnificPopup({
            delegate: 'a',
            type: 'image',
            mainClass: 'mfp-fade',
            removalDelay: 160,
            preloader: false,
            fixedContentPos: false,
            gallery: {
                enabled:true
            }
        });

        // Testimonial Slider
        $('.testimonials').slick({
            infinite: true,
            slidesToShow: 2,
            slidesToScroll: 2,
            autoplay: true,
            autoplaySpeed: 2000,
            dots: true,
            arrows: false,
            responsive: [
                {
                  breakpoint: 1420,
                  settings: {
                    arrows: false,
                    infinite: true,
                    slidesToShow: 2,
                    slidesToScroll: 2
                  }
                },
                {
                  breakpoint: 768,
                  settings: {
                    dots: false,
                    arrows: false,
                    infinite: true,
                    slidesToShow: 1,
                    slidesToScroll: 1
                  }
                },
                {
                  breakpoint: 480,
                  settings: {
                    dots: false,
                    arrows: false,
                    infinite: true,
                    slidesToShow: 1,
                    slidesToScroll: 1

                  }
                }
            ]
        });
        
        // Image Carousel
        $('.image-carousel').slick({
          centerMode: true,
          adaptiveHeight: true,
          centerPadding: '400px',
          slidesToShow: 1,
          slidesToScroll: 1,
          draggable: true,
          arrows: true,
          prevArrow: '<i class="droplet-arrow-right"></i>',
          nextArrow: '<i class="droplet-arrow-left"></i>',
          responsive: [
            {
              breakpoint: 1200,
              settings: {
                arrows: true,
                slidesToShow: 2,
                centerMode: false
              }
            },
            {
              breakpoint: 768,
              settings: {
                arrows: true,
                slidesToShow: 2,
                centerMode: false
              }
            },
            {
              breakpoint: 480,
              settings: {
                arrows: true,
                slidesToShow: 1,
                centerMode: false
              }
            }
          ]
        });

        // Recent Posts
        $('.recent-posts').slick({
            infinite: true,
            slidesToShow: 3,
            slidesToScroll: 3,
            autoplay: true,
            autoplaySpeed: 2000,
            dots: false,
            arrows: false,
            responsive: [
                {
                  breakpoint: 1024,
                  settings: {
                    dots: false,
                    infinite: false,
                    slidesToShow: 2,
                    slidesToScroll: 2
                  }
                },
                {
                  breakpoint: 768,
                  settings: {
                    dots: false,
                    infinite: false,
                    slidesToShow: 1,
                    slidesToScroll: 1
                  }
                }
            ]
        });
        
        // Mobile Navigation
        $('#mobile-navigation-btn').on('click', function (){
            $('#mobile-navigation').stop(true,true).slideToggle(300, 'easeOutCubic'); //easeInOutSine works also nice at 200ms
            return false;
        });
        $('#mobile-navigation .container ul li').each(function(){
            if($(this).find('> ul').length > 0) {
                 $(this).addClass('has-ul');
                 $(this).find('> a').append('<i class="droplet-angle-up"></i>');
            }
        });
        $('#mobile-navigation .container ul li:has(">ul") > a i').on('click', function (e){
            $(this).parent().parent().toggleClass('open');
            $(this).parent().parent().find('> ul').stop(true,true).slideToggle(300, 'easeOutCubic');
            return false;
        });

        // Header Search
        jQuery( document ).on('click', function () {
            jQuery( '.minisearch-wrap' ).hide();
        } );
        jQuery( '.minisearch-wrap' ).on('click', function (e) {
            e.stopPropagation();
        } );
        jQuery( '.minisearch-btn' ).on('click', function (e) {
            e.stopPropagation();
            if ( jQuery( '.minisearch-wrap' ).css( 'display' ) === 'block' ) {
                jQuery( '.minisearch-wrap' ).hide();
                jQuery( '.minisearch-wrap .minisearch-form input.minisearch-input' ).blur();
            } else {
                jQuery( '.minisearch-wrap' ).show();
                jQuery( '.minisearch-wrap .minisearch-form input.minisearch-input' ).focus();
            }
        } );

        // WooCommerce Quantity Field
        var parentSelector = $('.quantity');
        // If it's on the page
        if( parentSelector.length ) {
            var numberInputs = parentSelector.html();
            var textInputs = numberInputs.replace('type="number"', 'type="text"');
            var btnMore = '<button class="more">+</button>';
            var btnLess = '<button class="less">-</button>';
            parentSelector.append(textInputs + btnMore + btnLess);
            parentSelector.find('input[type="number"]').hide();
            $('.more, .less').on('click', function(e) {
                e.preventDefault();
                var newCounter = $(this).prevAll('input.qty[type="text"]');
                var oldCounter = $(this).prevAll('input.qty[type="number"]');
                var counterVal = newCounter.val();
                if( $(e.target).hasClass('more') ) {
                    counterVal++ ;
                } else {
                    counterVal-- ;
                }
                // Apply to both inputs
                newCounter.val(counterVal);
                oldCounter.val(counterVal);
            });
        }

    }); // End Ready Function

    // Gallery Post Type
    function ayesha_gallery(){

        var $gallery_container = $('.gallery-items');
        $('.gallery-item').css({visibility: "visible", opacity: "0"});

        $gallery_container.imagesLoaded( function() {
            $gallery_container.fadeIn(1000).isotope({
                transitionDuration: '0.6s',
                itemSelector: '.gallery-item',
                resizable: false,
                layoutMode: 'masonry', // masonry or fitRows
                sortBy: 'origorder'
            });

            $('.gallery-item').each(function(index){
                $(this).delay(80*index).animate({opacity: 1}, 200);
            });
        });

        $(window).resize(function() {
            $gallery_container.isotope('layout');
        });

        $('.gallery-filters a').on('click', function (){
            $('.gallery-items').addClass('animatedcontainer');
            $(this).closest('.gallery-filters').find('a').removeClass('active');
            $(this).addClass('active');
            var selector = $(this).attr('data-filter');
            var galleryID = $(this).closest('.gallery-filters').attr("data-id");
            $('.gallery-items[data-id=' + galleryID + ']').isotope({ filter: selector });
            return false;
        });
    }
    ayesha_gallery();

})(jQuery);
