(define complementer
  (lambda (rgb)
    (hsv->rgb (map inexact->exact(list (modulo(round(+ (rgb->hue rgb) 180))360) (rgb->saturation rgb) (rgb->value rgb))))))

(define analogous
  (lambda (rgb)
    (list
     (hsv->rgb
      (map inexact->exact 
           (list (modulo(round(+ (rgb->hue rgb) 30))360) (rgb->saturation rgb) (rgb->value rgb))))
     rgb
     (hsv->rgb(list (modulo(round(- (rgb->hue rgb) 30))360) (rgb->saturation rgb) (rgb->value rgb))))))

;will provide 4 tints
(define tints
  (lambda (rgb)
    (list
     (hsv->rgb (map inexact->exact (list (rgb->hue rgb) (rgb->saturation rgb) (* (rgb->value rgb) 1.5))))
     (hsv->rgb (map inexact->exact (list (rgb->hue rgb) (rgb->saturation rgb) (* (rgb->value rgb) 2))))
     (hsv->rgb (map inexact->exact (list (rgb->hue rgb) (rgb->saturation rgb) (* (rgb->value rgb) 2.5))))
     (hsv->rgb (map inexact->exact (list (rgb->hue rgb) (rgb->saturation rgb) (* (rgb->value rgb) 3)))))))

;will provide 4 shades
(define shades
  (lambda (rgb)
    (list
     (hsv->rgb (map inexact->exact (list (rgb->hue rgb) (rgb->saturation rgb) (* (rgb->value rgb) 0.6))))
     (hsv->rgb (map inexact->exact (list (rgb->hue rgb) (rgb->saturation rgb) (* (rgb->value rgb) 0.35))))
     (hsv->rgb (map inexact->exact (list (rgb->hue rgb) (rgb->saturation rgb) (* (rgb->value rgb) 0.2))))
     (hsv->rgb (map inexact->exact (list (rgb->hue rgb) (rgb->saturation rgb) (* (rgb->value rgb) 0.1)))))))


;(tints 16737095) produces '(16749674 16762510 16775089 16777173)
;(shades 16737095) produces '(10042154 5841432 3347214 1640711)
(define canvas (image-new 5 5))

;for (tints 16737095)
(image-set-pixel! canvas 0 0 16737095)
(image-set-pixel! canvas 0 1 16749674)
(image-set-pixel! canvas 0 2 16762510)
(image-set-pixel! canvas 0 3 16775089)
(image-set-pixel! canvas 0 4 16777173)

;for (shades 16737095)
(image-set-pixel! canvas 1 0 16737095)
(image-set-pixel! canvas 1 1 10042154)
(image-set-pixel! canvas 1 2 5841432)
(image-set-pixel! canvas 1 3 3347214)
(image-set-pixel! canvas 1 4 1640711)

#lang racket
(require gigls/unsafe)

(define triad
  (lambda (rgb)
    (list
     (hsv->rgb (map inexact->exact (list (modulo (round(+ (rgb->hue rgb) 150)) 360) (rgb->saturation rgb) (rgb->value rgb))))
     (hsv->rgb (map inexact->exact (list (rgb->hue rgb) (rgb->saturation rgb) (rgb->value rgb))))
     (hsv->rgb (map inexact->exact (list (modulo (round(+ (rgb->hue rgb) 210)) 360) (rgb->saturation rgb) (rgb->value rgb)))))))

(define ultimate-color-scheme
  (lambda (rgb)
    (display "ULTIMATE COLOR SCHEME TOOLKIT FOR")
    (display " ")
    (display rgb)
    (display "

")
    (display "Complement:")
    (display (complementer rgb))
    (display "
")
    (display "Analogous Colors:")
    (display (analogous rgb))
    (display "
")
    (display "Tints:")
    (display (tints rgb))
    (display "
")
    (display "Shades:")
    (display (shades rgb))
    (display "
")
    (display "Triad Colors:")
    (display (triad rgb))))
