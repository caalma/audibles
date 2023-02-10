# Composiciones


## in-tropo-deli (minitidal)

	stack[
	s "tabla ~!5 tabla2 ~!2" # n (irand 3)
	, s "bass:1 _ _ bass _ _ _ _ _ "
	, s "moog*8" # n ((irand 5) - (irand 2)) # cutoff (sine * 500) # gain 0.5
	, s "arpy*16" # n ((irand 2) - (irand 5)) # cutoff (saw * 700)  # gain 1.1
	]
	-- # silence

## nop-terrestre-bli-bla (minitidal)

	stack[
	n "1 ~ [0 8 _ ]*4 ~ ~ 0 1 ~ ~ " # s "808"
	, s "moog" # n (cycleChoose [2,7,5,0])  # cutoff 200
	, s "[arpy*3 ~ [arpy _ ]!5 ~!4]!1" # n (wchoose [(1, 0.1), (2, 0.9)]) # gain (rand + 0.2)
	, s "[~ bd*3 [hh _ ]!2 ~!8]" # n (wchoose [(0, 0.50), (1, 0.2), (2, 0.3)])
	, s "sine*12 _ _ _ _ _ sine _ _ _" # speed (irand 20)
	]

## no-tan-mii-long-aaah (minitidal)

	stack[
	s "db ~!6 hh ~!4" # n (irand 3)
	, s "bass ~!4 jvbass ~!6" # n (irand 4)
	, s "<909 808>*2" # n "<[1 3] [1 5] [0 7] [2 1]>"
	,  s "arpy*[12 | 9 | 15]" # n "<[2 3] [1 0] [1 3 1 5] [2 4 6]>" # gain (rand + sine - 0.2)
	, iter 4 $ slow 1 $  s "~ newnotes*5 ~" # n "<[0 11] [0 13 4] [0 2 7 10]>"
	]
	-- # silence

## alga-loop-e (minitidasl)

	stack [
	s "<bass!2 bass> ~*2 <bass bass*2 bass*3> ~" # n (irand 4) # gain 0.7 # pan (-0.4 + rand)
	, slow 3 $ s "bd"  # pan (0.2 + rand)
	, s "[hh!2 ~]*6" # n "[[0 1 0] | [2 3 0] | [4 3 0] | [2 1 0]]" # gain 0.6  # pan (-0.2 + rand)
	, s "arpy arpy*2 [arpy arpy*2]*2" # n "<[1 2] [3 4] [5 6] [7 8 9 0]>" # gain 0.7  # pan (0.6 + rand)
	]
	-- # silence

## alga-loop-e-silb-and-o (minitidal)

	stack [
	s "<bass!2 bass> ~*2 <bass bass*2 bass*3> ~" # n (irand 7) # gain 0.6 # pan (-0.4 + rand)
	, slow 3 $ s "bd"  # pan (0.2 + rand)
	, s "[hh!2 ~]*6" # n "[[0 1 0] | [2 3 0] | [4 3 0] | [2 1 0]]" # gain saw  # pan (-0.2 + rand)
	, s "newnotes newnotes*2 [newnotes [newnotes*2 | newnotes*3] ~]*2" # n "<[2 1] [4 1 0 3] [6 5] [0 8 7 0]>" # pan (0.6 + rand)
	]
	-- # silence

## en-corde-re-cuerdo (minitidal)

	s "[gtr*3 | ~] [gtr*2 | gtr] [gtr | ~] [gtr*5 | ~]"
    # note  (
	("[a | b | c | d | e | f | g]*4")
    | +  "[4 | 5]" |
    -- |+ "[s | f | ]"
    | + "['maj | 'min | ]" |
    -- |+ "[ '2 | '4 | '6 | ]"
    | + "['o | 'i | 'ii | ]" |
    |        |    |     |    |
    )
    # gain ((7 + (irand 3)) / 10)
    # pan sine
    -- # silence

## con-trarit-mic-a (minitidal)

	stack [
	juxBy 0.2 rev $ every 2 ("<0.25 0.125 0.5>" <~) $ n "0*2 [[~ 1] 3] 4 [0 3*2]" # s "[909 | 808 | feel]"
	, off 1.1 (# vowel "< a o a e o a e a i >") $ every 2 ("<-1 0.25 0.125>" <~) $n "0 <0 4> [2 0] [2 3]" # s "<arpy sine>" # speed "[3 | 1 | 0.1]"
	, juxBy 0.5 rev $ chunk 4 ((+ speed (1 + sine)) . ply 8) $ n "3(3,8)" # s "future"  # speed "<-1 1>"  # legato "<1 2 3>"
	]
    -- # silence
## peg-alent-o-ng-astra (minitidal)

	stack [
	s "909(3,8)" # n (shuffle 3 "0 1 5 7 8")
	, s "808(5,8)" # n (shuffle 5 "0 1 2 3 5 7 8 9 11 15")
	, s "bass3(2,8)" # n (shuffle 2 "0 1 5 7 8")
	, slow 4 $ s "moog" # n ((irand 4) + 6) # cutoff 200
	, slow "[ 2 | 3 | 1 | 0.5 ]" $ s "gtr" # note "[ f'min | c'maj | e'min'o | b'min'o | g'maj ]" # gain 0.8 # pan sine
	]
	-- # silence

## peg-alent-o-ng-marea (minitidal)

	stack [
	s "e(3,8)" # n (shuffle 3 "0 1 2 3 4 5 6 7 8 9") # gain 0.8
	, s "bd(5,8)" # n (shuffle 5 "0 1 2 3 5 6 7 8 9") # gain 0.8
	, s "bass3(2,8)" # n (shuffle 2 "0 3 5 7 11") # gain 0.8
	, slow 4 $ s "moog" # n "[ 0 | 3 | 5 | 9 ]" # cutoff 200 # pan tri # gain 0.7
	, slow "[ 2 | 3 | 1 | 0.5 ]" $ s "gtr" # note "[ f'min | c'maj'o | c'maj | e'min'o | a'min | b4'maj | g'maj ]" # gain 0.9 # pan sine
	]
	-- # silence
## tum-tan-tam-ten-tom

	stack [
	s "sn(<2 3>,7)"
	,s "bd(<3 4>,7)"
	,s "db([8 | 10],14)"
	,s "bass3(5,[14 | 7])"
	,slow "<3 2 1>" $ s "gtr" # note "[c'maj'o | e'min'o | g'maj'o | a'min'o]"
	,slow "[2 | 3 | 1]" $ s "tink(17,21)" # note (irand 12)
	,s "[drum | 909 | newnotes](13,14)" # n (palindrome "[0 1 2 3 4 | 4 2 6 3 | 0 3 5 1 | 9 3 2 5 1]") # gain 0.7
	]
	-- # silence

## tro-pi-e-zotini-e-bla (minitidal)

	stack[
	s "bd(3,4)"
	, s "hh(5,8)"
	, s "bass2(7,12)" # note "<12 1 6 3 10 2>"# cutoff 2000 # gain 0.7
	, slow "[ 0.25 | 0.5 | 1 | 2 | 4 ]" $ s "sax(2,5)" # note "[ g'maj | a'maj | d'min'o ]" # pan sine # gain 0.7
	, slow "<1 2 3 2>" $ s "[ future | e ](4,6)" # note (irand 12)
	]
	-- # silence

## tecni-cabip-ment-e-blup (minitidal)

	stack [
	n "1 ~ 2 ~!2 3 ~!2" # s "[arpy | newnotes]" # speed ((irand 3)+ (sine * 2))
	, slow 3 $ n "~ 0 ~ 0!2 1 ~ 0" # s "sax" # pan tri # gain 0.7

	, stack[
	n "[ [~ 1]!2 | [~ 1]!4 | [~ 1]!6]"  # s "909"
	, n "[0 ~]!4" # s "bass3"
	]

	, n "0 0*2 ~ 0/2 ~/2 0*3 ~ 0 ~"  # s "tink"
	, n "0!2 ~!2 1 ~ ~/2 0!2 ~ 0 ~!2" # s "tok"
	]
	-- # silence


## re-petid-asi-multan-ea (minitidal)

	slow "[0.9 | 1 | 1.1]"
	$ n "[ <0 1> [2 | 4 | 6] <0 1> [3 | 5 | 7] ]!4"
    # s "[808, tok, newnotes]"
    # gain 0.8
	-- # silence

## re-petid-asi-multan-eae-x-tracort-ada (minitidal)

    slow "[0.9 | 1 | 1.1]"
    $ n "[ <0 1> [2 | 4 | 6] <0 1> [3 | 5 | 7] ]!4"
    # s "[ [ 808 | 909 | ~], [tok | bass3], [newnotes | sine | arpy | ~ ] ]"
    # gain 0.8
    -- # silence

## pip-upi-pipi-pup-a (minitidal)

    stack [
    n "0 ~ 3 ~ 6 ~ ~ " # s "[[808 | e] , tink]"
    , n (palindrome "[0 2 4 6 8 9 | 1 3 2 4 5 8 | 1 5 2 0 7 4 ]") # s "newnotes"
    , slow "<2 3>" $ n "<0 3 5 9> _" # s "sine"
    , slow "<3 2>" $ n "0 ~ 2*2 ~ ~" # s "[ future | tok | bass3 ]"
    ] # pan sine
    -- # silence
