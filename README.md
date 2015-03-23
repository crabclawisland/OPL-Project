# OPL-Project



    #lang racket
     (require pict images/icons/control images/icons/style)
     (require images/icons/misc)
     (require images/logos)
     (require images/icons/stickman)
     
     ;;Step Icon superimposed on Record Icon;;
     
    (pict->bitmap
      (cc-superimpose
       (bitmap (record-icon #:color "forestgreen" #:height 32
                            #:material plastic-icon-material))
       (bitmap (step-icon #:color light-metal-icon-color #:height 15
                          #:material rubber-icon-material))))
      
      ;;Bomb Icon list with changed icon material and varying sizes;;
      
    (for/list ([material  (list plastic-icon-material
                              rubber-icon-material
                              glass-icon-material
                              metal-icon-material)]
            [height (list 30 35 40 45)])
    (bomb-icon #:height height #:material material))
      
      ;;Polygon List with cyclical color and icon material changes;;
     
       (for/list ([sides  (in-range 1 9)]
             [material  (in-cycle (list plastic-icon-material
                                        glass-icon-material
                                        metal-icon-material
                                        rubber-icon-material))]
             [color     (in-cycle (list "cornflowerblue" 
                                        "forestgreen" 
                                        "tomato"))])
  
    (regular-polygon-icon sides #:color color #:height 32
                          #:material material))
      
      ;;Stickman Running animation frames in list;;
      
      (for/list ([t  (in-range 0 1 1/12)])
    (running-stickman-icon t #:height 32))
    
    
