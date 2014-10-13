#  Edward William Lane, _An Arabic-English Lexicon_

The original files are from the Perseus Project at http://www.perseus.tufts.edu/hopper/collection?collection=Perseus:collection:Arabic

# goals

There are several problems with the original XML files from Perseus.
One is that they contain some errors - not surprising, considering the
magnitude of the task.  The other is that they use the
[Text Encoding Initiative](http://www.tei-c.org/index.xml) (TEI)
schema.  That schema is fine if the goal is to produce a digital
replica of an original text, but not so good if the goal is to produce
a lexical database.  It also does not handle Arabic very well.

The problem with a mere digital transcription of the original text is
that it reproduces its errors and structural inconsistencies.  If the
original text were of scholarly interest on its own, that would be
valuable; but in the case of Lane's Lexicon, we're dealing with what
is essentially one man's transcription and summarization of a largish
collection of original Arabic sources.  Qua text it is of little
interest.  Except for people interested in studying 19th century
British/Imperial schoolarship, nobody is interested in studying the
text of Lane's Lexicon itself.  They use to to study Arabic; they do
not study it as something of interest in itself.

So although having a digital transcription of Lane is not a bad thing,
it is only a start toward a digital lexical database, which is the
goal of this project.  Lane's original text contains lots of minor
errors, of course; but it also contains a lot of material that amounts
to clutter.  For example, the text is liberally peppered with
references to his sources.  This makes it harder to read and adds
little value; for who will (or has ever) checked his sources?  After
all, Lane is a secondary source; if you want the real thing, you
should be using the original Arabic dictionaries that Lane himself
used.

Lane's text also contains lots of structural material, but it is quite
inconsistent, at least from the perspective of modern data design.
For example, Lane often uses delimiters ('(', ')', '[', ']') to set
apart runs of texxt, but it is often unclear just why.  Furthermore,
unmatched delimiters within a structural element are common.  A fully
marked up version of such a text would use semantic markup
(e.g. <comment>...</comment>) instead of delimiter characters.  So one
problem with the Perseus version is that mapping from delimiter
characters to XML elements (e.g. '(...)' to '<paren>...</paren>')
results in an invalid XML structure, with orphaned open and close
tags.

Another example:  delimiters are sometimes mismatched, e.g. '( ... ]'.

The goal for this repository is primarily to correct the text, and
then, to a lesser extent, to convert the structure into a form more
suitable for database-like processing.

To fix delims, we use <sib:add>, <sib:del>, and <sib:swap>.

etc.

# license

The licensing of the originals is unclear.  See
[Perseus Copyrights & Warranty](http://www.perseus.tufts.edu/hopper/help/copyright).
I believe these files count as "public domain text", but on the website they are presented with "This work is licensed under a Creative Commons Attribution-ShareAlike 3.0 United States License."  The XML files contain only this:

```
<publicationStmt>
  <publisher>Trustees of Tufts University</publisher>
  <pubPlace>Medford, MA</pubPlace>
  <authority>Perseus Project</authority>
  <availability status="free">
    <p>This text may be freely distributed,
	   subject to the following restrictions:</p>

    <list>
      <item>You credit Perseus, as follows, whenever you use the document:
	    <quote>
	      Text provided by Perseus Digital Library,
		  with funding from The U.S. Department of Education
		  and The Max Planck Society.
	    </quote>
      </item>

      <item>You leave this availability statement intact.</item>
      <item>You offer Perseus any modifications you make.</item>
    </list>
  </availability>
</publicationStmt>

```
