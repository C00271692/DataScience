1. Found a good wikipedia dataset to train the RNN model on

2. The dataset implemetation in the notebook uses an outdated version of that datset, and newer versions dont seem to load from that tensorflow collection

3. At this stage there are too many issues with tensor flow, so i found a different package that contains a wikipedia dataset (hugging face)

4. Full datset is extremely large (20GB) worth of wikipedia articles

5. Downloading 1000 articles from the dataset instead of the full volume which would fill up my SSD

6. too many issues with that dataset, and its too large maybe find something else

7. Found a shakespeare dataset and notebook

8. Notebook example is very outdated and complicated, cluttered with too many redundant cells that just output data pieces, im mainly interestd in the algorithms for training/testing, not parsing and reparsing/cleaning data

9. Need to make changes such as removing the 'boring' stuff and replacing outdated tensorflow stuff in the notebook

10. First test of the model across small (10 epochs) we get a fairly bad output, with random words, some are even made up:
Creative writing (temperature=1.2):
Once upon a time to speak.
Mercy have decreation;
That bug of waked. Nay, melpo!
Speak not whyself mayor witn;
Hex here, think him's son had advertake.

ISEBELA:
Ungen! He sattle's welchis as tellsper;
It forward of thy news?
He pronouncling fears
Plack little from
the tongue.

YORK:
What here England?
A crack
And give me lightness.

SAMPSON:
Art to our hearts:
Lest seemins beas to tanker.
Hark you, A quarral,
Bear them for York
Lintlement made you
as for the fonours have thought; for duends, and I oscuded cuty,
Will not be more pity.

POLIXENES:
Great timbusiance of your great your cold
Till Kat and die,
im as mole beats,
Turns to some approbbricy?
But Jaulty, fright his sw-life-tahter of twentyaturn beats,
Errone is your brow;
A people-braced service,
Inless they alone, reparts
here comes here. Both sir, Coriolanuaps.

GON:
Know it ignormort in all my uncle,
His sword I'll paid in everine.

BUCKINGHAM:
His hard-beliech not. Brother Gaunt
Hath set upon this?
Ancounted ever I:
Your grunced dalving pay

11. Increased Epoch to 30 for better language learning and Increase model capacity

12. With these tweaks we get the following results, improved but not 100% coherent:
Generating Shakespeare text...

Romeo's lines:
ROMEO: My love for Juliet is befal.

HENRY BOLINGBROKE:
More hold that I said so? lay and beggary
Then resolute as we are.

GRUMIO:
My cake is dough; but I'll in among these words,
Infer favours shall be fearful.

HENRY BOLINGBROKE:
First, heaven be the worst that I should speak,
Before I stay: but I have stay'd
To tin thou shalt content that thou belike.'

Second Citizen:
Think you me all this whileld?

Shepherd:
Take hands, a bargain! and so doth he; and then
Lady:
Madam, I have one, and therein
Of March wash y sweet saluteth me?
Young son, it argues a thousand grains
And her re usurp'd or fruit;
Which was an adulteress;
For to my rest that love what he would have strickenge-stand, the prince Frorth,
Whose strange still, which will inform thee here.

ROMEO:
I have night's cloak:
Who now the priest shout self-born in all:
In all the throne names and undertakes,
And I will take thy word: yet if thou swear'st,
A thousand thanks, breed thee from the gods,
Who preserves to save and by joy!

TRANIO:
Ay, marry, am I, s

13. For a relitavely light RNN model with 4 layers as a start i think it does decently. We have characters that are engaging somehats, and ask questions. Some statements are ended with a colon (:) as is common ins the original Shakespearean text, which shows that the model does in fact learn, but is very limited in a simple RNN form. To get the model more accurate sentences we would need to delve into Transformers and context keeping etc etc.

14. Found that too high temperature generates too many made up words and no context whatsoever due to randomness. The smaller the temperature the more and coherent the sentences are (temperature=0.4):

Hamlet's soliloquy: 
HAMLET: To be, or not to be part,
Let me except the time to come.

JULIET:
O God, I have a noble memory; what of him?
Our slaught and grief is now born to repend.

JULIET:
I do confess it, Tranio, for the face
Be merry, gods. Imply that know it.

GLOUCESTER:
The queen is valued thirty.

WARWICK:
How now, my heart! how now, what news with you,
She hath a poor men of this.

JULIET:
I will tell thee, Let me be thus bold.

LADY ANNE:
I would I knew thy heart.
...
For learning me your language!

PETRUCHIO:
No, couple mouths

15. An extremely low temperature causes the model to always choose the highest probabilty output node, beacuse of lack of variation in the output nodes, there is barely any new progress in the text and the same phrases will be repeated in a loop:

Creative writing:
Once upon a time
Show much like to make thee sigh.

PETRUCHIO:
Come, come, he hath murdered my mistress' grace,
As 'twere a courteer,
That cannot do thee,
And for thy master.

Third Citizen:
Clubs, bills, and quite lost their heads shall pay thee, father, so it must needs be.

MENENIUS:
I am, as thou art,
Commit'st thy ears?

Citizens:
Down with the Capitol.

All:
We will some other but mean to besiege you in your children?

LADY CAPULET:
That is the cause of Lancaster usurps the precipitation fled:
Did I henceforth thou art to set
The people against my oath;
As I did seem to kiss it argues; and
therefore in heaven bless thee! Hark you, sir.

CORIOLANUS:
The gods have well prevented.
She will deserve your life?

KING RICHARD III:
Ay, if the county serve thy bed,
Until that part the fray?
'Con tutto it bred by no means
To be o'erpower'd; and in this as thou art,
Commit'st thy ears?

Citizens:
Down with the Capitol.

All:
We will some other but mean to besiege you in your children?

LADY CAPULET:
That s