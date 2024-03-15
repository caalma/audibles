# Composiciones

## son-aracay-a-lla

    ##minitidal

    slow 2 $ stack [
    striate 10 $ n (stitch "t*2 f  f ~ f ~" 1 2) # s "bd" # resonance 2
    , striate' 7 0.4 $ n "1 ~ ~ 2 ~" # s "bajo" # speed 0.6
    ]
    -- # silence

## hi-pnotiz-a-ralc-i-clar

    ##minitidal

    stack [
    n "0..5(<9 6 3>, <12 7>)" # s "bajo" # up (slow 9 perlin)
    , n "0..5(<12 9>, <9 12 6>)" # s "tumba" # up (fast 9 perlin)
    ]

## sindes-canz-oho-y

    ##minitidal

    stack [
    contrast (# speed "<2 -1>") (rev)  (n "<2? 3 5? 7>") $ n "0..8" # s "bass"
    , slow "3 0.3" $ chunk' "2 3" (# speed "0.4 0.2") $ sound "gtr*<8 7 9>" # gain 0.7
    ]
    -- # silence

## lab-erint-oo-toñer-o

    ##minitidal

    stack [
    n "~ ~ 0(5,<8 9>)" # s "sprvibe" # note "c"
    , n "~ 0(6,<7 9>)" # s "sprvibe" # note "g"
    , n "0(7,<8 9>)" # s "sprvibe" # note "e"

    , stack [
    n "0(2?,<6 9>)" # s "tumba" # note "c"
    , n "~ 0(2?,<5 9>)" # s "tumba" # note "g"
    , n "~ ~ 0(2?,<6 9>)" # s "tumba" # note "e"
    ]

    ]

    -- # silence


## primerencuentro

    ##minitidal

    stack [

    stack [
    n "0(4,<8 9>)" # s "tumba" # note "c"
    , n "0(5,<7 9>)" # s "tumba" # note "<g f?>"
    , n "0(3,<8 9>)" # s "tumba" # note "e c"
    ] # gain "1 0.4 0"

    ,  stack [
    n "0(5,<8 9>)" # s "tumba" # note "c"
    , n "0(4,<7 9>)" # s "tumba" # note "<g d?>"
    , n "0(3,<8 9>)" # s "tumba" # note "<a? e>"
    ] # gain "0 1 0.4"

    ,  stack [
    n "0(6,<8 9>)" # s "tumba" # note "g"
    , n "0(2,<7 9>)" # s "tumba" # note "<c e?>"
    , n "0(7,<8 9>)" # s "tumba" # note "<g c e>"
    ] # gain "0.4 0 1"


    ]
    -- # silence


## sab-anados-pmll-o-vizna

    ##minitidal

    degradeBy 0.1 $ stack [
    n "<0 2 4>(3,<9 7>)" # s "sprvibe" # cutoff "200 1600?"
    , n "<5 7 9 12 >(5,<7 9>)" # s "sprvibe" # cutoff "300? 100 3000"
    , n "<15 17>(6,<9 7>)" # s "sprvibe" # cutoff "1600 200"
    ] # resonance "0.2 0.8" # pan perlin
    -- # silence


## pa-receco-no-cido

    ##minitidal

    stack [
    slow "[0 | 0.5 | 1 | 2 | 3]" $ n "<0 1>(2, 16)" # s "808mc"
    , n "<1 2 3>(<4 8 12>,16)" # s "tok"
    , n "<4 3>(<5*2 7 9>,16)" # s "808hc"
    ]
    -- a# silence


## brasama-n-darina

    ##minitidal

    stack [
    slow "[0 | 0.5 | 1 | 2 | 3]" $ n "<0 1>([2 4 6], 16)" # s "tumba"
    , n "<1 2 3>(<4 8 12>,16)" # s "chin*3 tok"
    , n "<4 3 0>(<5*2 7 9>,16)" # s "tok can*5"
    ]
    -- # silence


## hi-e-rbas-e-canue-vep-m

    ##minitidal
    slow "1 0.5 2" $ stack [
    slow "[0 | 1]" $ n "<7 6>(3, 19)" # s "stomp tumba"  # gain 0.9
    , n "<2 1 1 2 1 2>(<7>,19)" # s "tumba stomp" # gain 0.8
    , n "<0 1 0 0 1>(<11>,19)" # s "tok tink"  # gain 0.7
    , degradeBy 0.6 $ slow "3 1 2" $ n "0(12, 19)" # s "ul" # speed "0.3 1 2" # (slow "0.1 1 2" $ note "<[c6, e4, g6] e g6 [a, b6] [a7, f7, d7] d6 c5>") # pan perlin # resonance "0 2"
    ]
    -- # silence

## rondap-e-ripatet-i-ca

    ##minitidal

    stack [
    slow "[0 | 1]" $ n "<7 6>(3, 19)" # s "stomp"  # gain 0.9
    , n "<2 1 1 2 1 2>(7,19)" # s "stomp" # gain 0.8
    , n "<0 1 0 0 1>(5,19)" # s "stomp"  # gain 0.7
    , n "0(9, 19)" # s "sprvibe" # speed 0.5 # (slow 0.16 $ note "<c6 e4 g6 e g6  d6 c5>") # cutoff "<250 750 200 800>"
    ]
    -- # silence


## desca-m-padon-u-blado

    ##minitidal

    stack [
    slow "[0 | 1]" $ n "<7 6>(3, 19)" # s "stomp"  # gain 0.9
    , n "<2 1 1 2 1 2>(7,19)" # s "tok" # gain 0.8
    , n "<0 1 0 0 1>(5,19)" # s "[tink | stomp]"  # gain 0.7
    , degradeBy 0.4 $ n "[0 | 2 | 4 | 8](9, 19)" # s "wind" # speed "0.3 0.2" # (slow 0.16 $ note "<c6 e4 g6 e g6  d6 c5>") # cutoff "[250 | 750 | 200 | 800]" # gain 0.6
    ] # resonance perlin

    -- # silence

## re-piteo-nor-epit-e

    ##minitidal

    stack[

    degradeBy 0.1 $ stack[
    slow 1 $ n "~ 0 ~ ~ ~ ~ ~ 0" # s "808hc" -- 01000001
    , slow "1 2 0.5" $ n "1(2,8)" # s "808mt" -- 10001000
    , slow "2 4" $ n "2(3,8)" # s "808mc" -- 10010010
    , slow "4 2" $ n "3(5,8)" # s "808lt" -- 10110110
    ]  # pan perlin

    , degradeBy 0.4 $ slow "0.3"  $ n "0" # speed "0.1 1.1 11" # (slow 2 $ note "[d5'maj | d6'min | d7'maj'o]" # s "sitar") # cutoff "1200 100 20000" # end "0.05 0.03 0.3 1" # gain perlin
    ]
    -- #silence


## auy-entasu-e-ños

    ##minitidal

    stack[

    stack[
    sometimes (rev) $ n "[0 | 1](<3 4>,8)" # s "quinto" # speed "[0.9, -0.8]"
    , n "<1 2>(<7 9 3>,16)" # s "quinto"
    ] # cutoff "100 800 50 1500" # slow 4 (gain ((perlin + sine)*0.8)) # resonance 0.6

    , sometimesBy 0.4 (# silence ) $ stack[
    rev $ n "2(<3 5 7 5>, 16)" # s "uxay" # note ((run 5) * "<1 -1>") # hcutoff "2000" # speed 0.8
    , sometimesBy 0.8 (# speed perlin) $ n "2(<9 11>, 16)" # s "sprvibe" # begin 0.2 # end 0.5
    ] # (slow 0.2 $ note "<[e g c] a [d b g] c [f d e] b>")

    ]
    -- #silence


## ti-errades-o-lada

    ##minitidal

    stack[

    n "0(<5 6>,8)" # s "bend"
    , rev $ n "1(3,8)"  # s "bend"
    , n "~ 2*2 ~"  # s "bend"
    , sometimes (# silence) $ sometimes (rev) $ slow "<2 3>" $ n "3(5,8)"  # s "bend" # speed ("[0.3 | 0.5 | 0.1]" * "<1 -1>") # gain 0.8
    , n "[0?, ~ 1, ~!3 4?*2 ~]" # s "lt" # speed "[0.3, 0.5, 0.1]"
    , slow 2 $ s "[~ sax:15, ~ sax:<0 5 10 20>? ~]" # speed ("0.8" * "[1 | -1]") # gain (0.6 + (irand 30)/100)

    ]  # (slow 2 $ note "<d f [a, e] c [e, g]>")
    -- #silence

## fi-gurafo-n-do

    ##minitidal

    stack[

    stack[
    sometimesBy 0.7 (rev) $ n "[0 | 1](<3 4>,8)" # s "tumba" # speed "[0.9, -0.8]"
    , n "<1 2>(<7 9 3>,16)" # s "tok"
    ] # gain 0.7

    , stack[
    n "[0 | 1](3, [9 | 7 | 11])" # s "em2" # gain "[0.6 | 0.7 | 0.8 | 0.9]"
    ,sometimesBy 0.6 (rev) $ slow 10 $ n "3" # s "em2" # speed "0.1" # hcutoff 1000
    ] # (slow 4 $ pan sine)

    ] # resonance 0.3

    -- # silence


## ci-closimp-u-ntuales

    ##minitidal

    slow 0.1 $ stack [
    slow 3 $ n "0" # s "sid"
    , slow 5 $ n "1" # s "sid"
    , slow 7 $ n "2" # s "sid"
    , slow 11 $ n "3" # s "sid"
    , slow 13 $ n "4" # s "sid"
    , slow 17 $ n "5" # s "sid"
    , slow 19 $ n "7" # s "sid"
    , slow 23 $ n "8" # s "sid"
    , slow 29 $ n "9" # s "sid"
    ]
    -- # silence

## tub-oslat-asbotel-lasfu-egoins-ectos

    ##minitidal

    stack [
    n "[0(<1 5 7>, 8) , 1(3, 8)]" # s "[tumba , bottle?]"
    , n "[0(4, 8) , 1(<2 6>, 8)]" # s "[bin | mt?]"
    , slow 10 $ n "0" # s "sheffield" # gain 0.8
    , slow 6 $ n "0 " # s "fire"
    , slow "[0.25 | 0.5 | 1 | 2 | 4]" $ n "<2 1 0>" # s "sprvibe" # speed 0.3 # gain 1.2 # note "<a? b? c e g>"
    ]
    -- # silence

## toc-argol-pearper-cuti-rya

	##minitidal

	stack [
	n "<0 1 2>(4, 8)" # s "uxay"
	, n "[0(5, 8) , 1(3, 8)]" # s "tumba"
	, degradeBy 0.3 $ n "<0 2>(6, 8)" # s "quinto" # gain 0.7
	, slow "[0 | 3 | 5]" $ n "0" # s "tink" # speed "[-0.1 | 0.1]" # note "[a | g | d]" # gain 1.4
	, slow "[0 | 1 | 2]" $ degradeBy 0.25 $ n "2 4 [8 | 10] 16 [13 | 15] 11 7 [1 | 3] " # s "sprvibe" # gain 0.8
	]
	-- # silence

## e-spacios-op-ormelod-i-co

	##minitidal

	stack [
	slow 2 $ n "1*2 0 0*2 1" # s "[bottle?0.2, can?0.7, chin?0.1]" # n (irand 2)
	, slow "[2 | 3]" $ n "<0 1>" # s "gtr" # (slow 2 $ note "a g e c b") # speed "<-0.3 0.3>"
	, degradeBy 0.1 $ slow 2 $ n "[3 | 4](5, <8 16>)" # s "made" # (slow 0.2 $ note "a g e c b")
	]
	-- # silence

## e-stirad-ocord-iformeap-a-jaread-o

	##minitidal

	stack [
	slow "[3 | 5 | 7]" $ n "[0 ~? 1]*2 ~ [1? 0 2 1] ~ 0 _ [1 3]![3 | 2] ~!2" # s "[bass3?0.2, cpluck?.6, coins?]" # (slow "<2 1>" $ note "<1 4 8 7 5 3 2 0>")
	, slow "[40 | 45]" $ n "0 1 0 2 1 3 1 4 2 5 2 6 4 3 5 3 6 4 2 1" # s "cbow"  # (slow 2 $ note "[-3 | 3 | 0]") # gain 0.8
	, slow 4 $ n "[1 | 2 | 3 | ~](3, [7 | 11 | 13 | 17])" # s "ades4"
	]
	-- # silence

## tran-qui-pan-qui

	##minitidal

	swing (2/6) $
	stack [
	n "[0 | 8 | 9](2,6)" # s "ht"
	, n "~!2 [2 | 3]" # s "east"
	, n "<11 12 13 15>(3,6)" # s "dr_few"
	, n (irand 6) # s "[house | hit]"
	, slow "[2 | 4 | 6]" $ n "[1 | 0]" # s "[coins | em2]"
	, slow 3 $ n "0 3 4 8 13 1 5 7 9 2" # s "flbass"
	, slow "<2 3 1 4 1>" $ note "<c'maj g'min'o e'min bf'o>" |+ note "[-24 | -12 | 0 | 12 | 24]" # s "cpluck"
	]
	-- # silence

## disco-r-dinan-te

	##minitidal

	stack [
	n "<1 2 3 5 6>(3, 15)" # s "[909 | 808]"
	, n "[1 | 2 | 3 | 5 | 6](2, 7)" # s "[909 | 808]"
	, s "newnotes(11,17)"  #  n (irand 12)
	, slow 3 $ s "gtr(3, 5)" # note "[c'maj | g'min | d'min'7 | a'min'7'o] <c'maj g'min>" |+ note (6 + (irand 5))
	]
	-- # silence

## lu-gubr-e

	##minitidal

	stack [
	n "0 ~ ~ 0 1 ~ 1 2 1 0 ~ ~" # s "arp" # end 1
	, slow 5 $ n "<0 3 5 6 3 5 6 0> <1 2 3> ~" # s "moog"
	, n (irand 12) # s "newnotes(4,9)"
	]
	-- # silence

## in-terve-n-idoreg-ula-r

	##minitidal

	swing ("[6 | 3]" / 8) $
	degradeBy 0.1 $
	stack [
	note "<e f>(4,8)" # s "jvbass"
	, note "<c g a>(6,8)" # s "bass3"
	, note "b(2,8)" # s "tok" # gain 1.4

	, s "gtr" # note "c([0 | 1 | 2],8)" |+ note  "[12 | -12 | 6 | -6]"
    # begin "0.4" # end  "[0.8 | 1.2]"
    # bandf "[20, 200, 500, 1000, 3000, 2000, 4000, 10000]" # gain 1.7

	]
	-- # silence

## int-erven-irirreg-u-lar

	##minitidal

	degradeBy 0.1 $
	stack [
	n "<0 3>(4,9)" # s "jvbass"
	, n "<0 2 4>(5,9)" # s "bass3"
	, swing (4/7) $ n "0(4,7)" # s "tok" # gain 1.4

	, n "0([2 | 1],7)" # s "gtr" |+ note ((irand 3) + "<0 3 7 11>")
    # begin "0.2" # end  "[0.4 | 0.5]"
    # bandf "[20, 200, 500, 1000, 3000, 2000, 4000, 10000]"
    # gain 1.7
	]
	-- # silence

## ent-a-rrad-oys-u-mergid-o

	##minitidal

	stack [
	degradeBy 0.7 $ n "[0 | 9]*17" # s "tok" # gain 1.3
	, degradeBy 0.5 $  n "<0 2 3 5>*9" # s "[bass3 | jvbass]" # speed (0.4 + sine )
	, slow 3 $ note "[c e g b](5,7)" # s "sax" |+ note (5 + "<4 7 2>") # hcutoff 1000 # resonance "0.9"
	]
	# bandf (100 + (sine * 2000)) # gain 1.7
	-- # silence

## conv-e-rgen-ci-ante

	##minitidal

	degradeBy 0.1 $
	stack [
	n "<[0 1 0 2] [7 2 5 1] [8 4 2 0 1 3]>" # s "tok" # gain 1.3
	, n "<1 [3 | 5]>([4 | 5], 6)" # s "bass3"
	, degradeBy 0.25 $ n "<1 2 3 4>_ <3 4> <5 6 7>__ <2 3>___ <7 8 9 10> <0 1>_" |+ note (irand 6) # s "<e newnotes future>"
	, every 3 rev $ s (overlay "newnotes(2,6)" "arpy(4,6)") # n "<2 1> 0 <3 5> <7 1 0>" # speed "0.1 <0.3 -0.4> -1 1"
	]
	-- # silence

## pip-upi-pipi-pup-a

    ##minitidal

    stack [
    n "0 ~ 3 ~ 6 ~ ~ " # s "[[808 | e] , tink]"
    , n (palindrome "[0 2 4 6 8 9 | 1 3 2 4 5 8 | 1 5 2 0 7 4 ]") # s "newnotes"
    , slow "<2 3>" $ n "<0 3 5 9> _" # s "sine"
    , slow "<3 2>" $ n "0 ~ 2*2 ~ ~" # s "[ future | tok | bass3 ]"
    ] # pan sine
    -- # silence

## re-petid-asi-multan-eae-x-tracort-ada

    ##minitidal

	slow "[0.9 | 1 | 1.1]"
    $ n "[ <0 1> [2 | 4 | 6] <0 1> [3 | 5 | 7] ]!4"
    # s "[ [ 808 | 909 | ~], [tok | bass3], [newnotes | sine | arpy | ~ ] ]"
    # gain 0.8
    -- # silence

## re-petid-asi-multan-ea

    ##minitidal

	slow "[0.9 | 1 | 1.1]"
	$ n "[ <0 1> [2 | 4 | 6] <0 1> [3 | 5 | 7] ]!4"
    # s "[808, tok, newnotes]"
    # gain 0.8
	-- # silence

## tecni-cabip-ment-e-blup

    ##minitidal

	stack [
	n "1 ~ 2 ~!2 3 ~!2" # s "[arpy | newnotes]" # speed ((irand 3)+ (sine * 2))
	, slow 3 $ n "~ 0 ~ 0!2 1 ~ 0" # s "sax" # pan tri # gain 0.7

	, stack [
	n "[ [~ 1]!2 | [~ 1]!4 | [~ 1]!6]"  # s "909"
	, n "[0 ~]!4" # s "bass3"
	]

	, n "0 0*2 ~ 0/2 ~/2 0*3 ~ 0 ~"  # s "tink"
	, n "0!2 ~!2 1 ~ ~/2 0!2 ~ 0 ~!2" # s "tok"
	]
	-- # silence

## tro-pi-e-zotini-e-bla

    ##minitidal

	stack [
	s "bd(3,4)"
	, s "hh(5,8)"
	, s "bass2(7,12)" # note "<12 1 6 3 10 2>"# cutoff 2000 # gain 0.7
	, slow "[ 0.25 | 0.5 | 1 | 2 | 4 ]" $ s "sax(2,5)" # note "[ g'maj | a'maj | d'min'o ]" # pan sine # gain 0.7
	, slow "<1 2 3 2>" $ s "[ future | e ](4,6)" # note (irand 12)
	]
	-- # silence

## tum-tan-tam-ten-tom

	##minitidal

	stack [
	s "sn(<2 3>,7)"
	, s "bd(<3 4>,7)"
	, s "db([8 | 10],14)"
	, s "bass3(5,[14 | 7])"
	, slow "<3 2 1>" $ s "gtr" # note "[c'maj'o | e'min'o | g'maj'o | a'min'o]"
	, slow "[2 | 3 | 1]" $ s "tink(17,21)" # note (irand 12)
	, s "[drum | 909 | newnotes](13,14)" # n (palindrome "[0 1 2 3 4 | 4 2 6 3 | 0 3 5 1 | 9 3 2 5 1]") # gain 0.7
	]
	-- # silence

## peg-alent-o-ng-marea

    ##minitidal

	stack [
	s "e(3,8)" # n (shuffle 3 "0 1 2 3 4 5 6 7 8 9") # gain 0.8
	, s "bd(5,8)" # n (shuffle 5 "0 1 2 3 5 6 7 8 9") # gain 0.8
	, s "bass3(2,8)" # n (shuffle 2 "0 3 5 7 11") # gain 0.8
	, slow 4 $ s "moog" # n "[ 0 | 3 | 5 | 9 ]" # cutoff 200 # pan tri # gain 0.7
	, slow "[ 2 | 3 | 1 | 0.5 ]" $ s "gtr" # note "[ f'min | c'maj'o | c'maj | e'min'o | a'min | b4'maj | g'maj ]" # gain 0.9 # pan sine
	]
	-- # silence

## peg-alent-o-ng-astra

    ##minitidal

	stack [
	s "909(3,8)" # n (shuffle 3 "0 1 5 7 8")
	, s "808(5,8)" # n (shuffle 5 "0 1 2 3 5 7 8 9 11 15")
	, s "bass3(2,8)" # n (shuffle 2 "0 1 5 7 8")
	, slow 4 $ s "moog" # n ((irand 4) + 6) # cutoff 200
	, slow "[ 2 | 3 | 1 | 0.5 ]" $ s "gtr" # note "[ f'min | c'maj | e'min'o | b'min'o | g'maj ]" # gain 0.8 # pan sine
	]
	-- # silence

## con-trarit-mic-a

    ##minitidal

	stack [
	juxBy 0.2 rev $ every 2 ("<0.25 0.125 0.5>" <~) $ n "0*2 [[~ 1] 3] 4 [0 3*2]" # s "[909 | 808 | feel]"
	, off 1.1 (# vowel "< a o a e o a e a i >") $ every 2 ("<-1 0.25 0.125>" <~) $n "0 <0 4> [2 0] [2 3]" # s "<arpy sine>" # speed "[3 | 1 | 0.1]"
	, juxBy 0.5 rev $ chunk 4 ((+ speed (1 + sine)) . ply 8) $ n "3(3,8)" # s "future"  # speed "<-1 1>"  # legato "<1 2 3>"
	]
    -- # silence

## en-corde-re-cuerdo

	##minitidal

	s "[gtr*3 | ~] [gtr*2 | gtr] [gtr | ~] [gtr*5 | ~]"
    # note  (
	("[a | b | c | d | e | f | g]*4")
    |+ "[4 | 5]"
    -- |+ "[s | f | ]"
    |+ "['maj | 'min | ]"
    -- |+ "[ '2 | '4 | '6 | ]"
    |+ "['o | 'i | 'ii | ]"
    )
    # gain ((7 + (irand 3)) / 10)
    # pan sine
    -- # silence

## alga-loop-e-silb-and-o

    ##minitidal

	stack [
	s "<bass!2 bass> ~*2 <bass bass*2 bass*3> ~" # n (irand 7) # gain 0.6 # pan (-0.4 + rand)
	, slow 3 $ s "bd"  # pan (0.2 + rand)
	, s "[hh!2 ~]*6" # n "[[0 1 0] | [2 3 0] | [4 3 0] | [2 1 0]]" # gain saw  # pan (-0.2 + rand)
	, s "newnotes newnotes*2 [newnotes [newnotes*2 | newnotes*3] ~]*2" # n "<[2 1] [4 1 0 3] [6 5] [0 8 7 0]>" # pan (0.6 + rand)
	]
	-- # silence

## alga-loop-e

	##minitidal

	stack [
	s "<bass!2 bass> ~*2 <bass bass*2 bass*3> ~" # n (irand 4) # gain 0.7 # pan (-0.4 + rand)
	, slow 3 $ s "bd"  # pan (0.2 + rand)
	, s "[hh!2 ~]*6" # n "[[0 1 0] | [2 3 0] | [4 3 0] | [2 1 0]]" # gain 0.6  # pan (-0.2 + rand)
	, s "arpy arpy*2 [arpy arpy*2]*2" # n "<[1 2] [3 4] [5 6] [7 8 9 0]>" # gain 0.7  # pan (0.6 + rand)
	]
	-- # silence

## no-tan-mii-long-aaah

    ##minitidal

	stack [
	s "db ~!6 hh ~!4" # n (irand 3)
	, s "bass ~!4 jvbass ~!6" # n (irand 4)
	, s "<909 808>*2" # n "<[1 3] [1 5] [0 7] [2 1]>"
	,  s "arpy*[12 | 9 | 15]" # n "<[2 3] [1 0] [1 3 1 5] [2 4 6]>" # gain (rand + sine - 0.2)
	, iter 4 $ slow 1 $  s "~ newnotes*5 ~" # n "<[0 11] [0 13 4] [0 2 7 10]>"
	]
	-- # silence

## nop-terrestre-bli-bla

    ##minitidal

	stack [
	n "1 ~ [0 8 _ ]*4 ~ ~ 0 1 ~ ~ " # s "808"
	, s "moog" # n (cycleChoose [2,7,5,0])  # cutoff 200
	, s "[arpy*3 ~ [arpy _ ]!5 ~!4]!1" # n (wchoose [(1, 0.1), (2, 0.9)]) # gain (rand + 0.2)
	, s "[~ bd*3 [hh _ ]!2 ~!8]" # n (wchoose [(0, 0.50), (1, 0.2), (2, 0.3)])
	, s "sine*12 _ _ _ _ _ sine _ _ _" # speed (irand 20)
	]
	-- # silence

## in-tropo-deli

    ##minitidal

	stack [
	s "tabla ~!5 tabla2 ~!2" # n (irand 3)
	, s "bass:1 _ _ bass _ _ _ _ _ "
	, s "moog*8" # n ((irand 5) - (irand 2)) # cutoff (sine * 500) # gain 0.5
	, s "arpy*16" # n ((irand 2) - (irand 5)) # cutoff (saw * 700)  # gain 1.1
	]
	-- # silence
