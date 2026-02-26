# 087：-Cryptography1, Video 10- IND-CPA Summary.zh_en - GPT中英字幕课程资源 - BV1VhEhzMEPL

Okay to recap NCPA one final time with all of the text on one slide for you to see。

 this is what the game looks like and it's helping us model whether or not a scheme is secure。

 So Eve first gets a chance to exercise her powers and maybe she uses this time to learn something about the scheme she sends a message and Alice faithfully encrypts it with her key。

 she can repeat this polynomially many times so she can't do this forever。

 but she can do this within a reasonable amount of time Eventually Eve feels pretty comfortable。

 she thinks she's gotten some advantage maybe and she initiates the challenge and to initiate the challenge you send two plain texts of the same length for example。

 cat and dog you send them to Alice， she turns around and Eve can't see what Alice is doing and she flips a coin if it heads。

 she encrypts cat if its tails， she encrypts dog and she sends the encrypted message back to Eve who doesn't know which one is encrypted At this point Eve gets a second chance to exercise her powers。

She can ask Alice to encrypt things of her choosing。 Alice will faithfully encrypt them。

 And once Eve is confident in her guess， she's going to commit to saying you encrypted cat or you encrypted dog。

 And if Eve can guess right with better than one half plus negligible probability。

 it means that Eve is breaking this scheme， she is learning something about the key or how the scheme works。

 and this scheme is not secure。 And by contrast， if Eve is never able to guess with better than 50% probability。

 this scheme is secure。 So that's the game in a nutshell and it allows us to analyze schemes for their security and their confidentiality。

