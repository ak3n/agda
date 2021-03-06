.. _command-line-options:

********************
Command-line options
********************

Command-line options
--------------------

Agda accepts the following options.

General options
~~~~~~~~~~~~~~~

:samp:`--version -V`
      Show version number

:samp:`--help[={TOPIC}] -?[{TOPIC}]`
      Show basically this help, or more help about :samp:`{TOPIC}`.
      Current topics available: ``warning``.

:samp:`--interactive -I`
      Start in interactive mode (no longer
      supported)

:samp:`--interaction`
      For use with the Emacs mode (no need to invoke
      yourself)

:samp:`--interaction-json`
    For use with other editors such as Atom (no need to invoke
    yourself)

:samp:`--only-scope-checking`
      Only scope-check the top-level module,
      do not type-check it

Compilation
~~~~~~~~~~~

See :ref:`compilers` for backend-specific options.

:samp:`--no-main`
      Do not treat the requested module as the main module
      of a program when compiling

:samp:`--compile-dir={DIR}`
      Set :samp:`{DIR}` as directory for
      compiler output (default: the project root)

:samp:`--no-forcing`
      Disable the forcing optimisation

:samp:`--with-compiler={PATH}`
      Set :samp:`PATH` as the executable to call to compile
      the backend's output (default: ghc for the GHC backend).

Generating highlighted source code
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:samp:`--vim`
      Generate Vim_ highlighting files

:samp:`--latex`
      Generate LaTeX with highlighted source code (see
      :ref:`generating-latex`)

:samp:`--latex-dir={DIR}`
      Set directory in which LaTeX files are
      placed to :samp:`{DIR}` (default: latex)

:samp:`--count-clusters`
      Count extended grapheme clusters when
      generating LaTeX code (see :ref:`grapheme-clusters`)

:samp:`--html`
      Generate HTML files with highlighted source code (see
      :ref:`generating-html`)

:samp:`--html-dir={DIR}`
      Set directory in which HTML files are placed
      to :samp:`{DIR}` (default: html)

:samp:`--css={URL}`
      Set URL of the CSS file used by the HTML files to
      :samp:`{URL}` (can be relative)

:samp:`--html-highlight=[code,all,auto]`
      Whether to highlight non-Agda code as comments in
      generated HTML files (default: all;
      see :ref: `generating-html`)

:samp:`--dependency-graph={FILE}`
      Generate a Dot_ file :samp:`{FILE}`
      with a module dependency graph

Imports and libraries
~~~~~~~~~~~~~~~~~~~~~

(see :ref:`package-system`)

:samp:`--ignore-interfaces`
      Ignore interface files (re-type check everything, except for
      builtin and primitive modules)

:samp:`--ignore-all-interfaces`
      Ignore *all* interface files, including builtin and primitive
      modules; only use this if you know what you are doing!

:samp:`--local-interfaces`
      Read and write interface files next to the Agda files they
      correspond to (i.e. do not attempt to regroup them in a
      :samp:`_build/` directory at the project's root).

:samp:`--include-path={DIR} -i={DIR}`
      Look for imports in
      :samp:`{DIR}`

:samp:`--library={DIR} -l={LIB}`
      Use library :samp:`{LIB}`

:samp:`--library-file={FILE}`
      Use :samp:`{FILE}` instead of the
      standard libraries file

:samp:`--no-libraries`
      Don't use any library files

:samp:`--no-default-libraries`
      Don't use default library files

.. _command-line-pragmas:

Command-line and pragma options
-------------------------------

The following options can also be given in .agda files in the
``{-# OPTIONS --{opt₁} --{opt₂} ... #-}`` form at the top of the file.

Caching
~~~~~~~

:samp:`--caching`
      Enable caching of typechecking (default)

:samp:`--no-caching`
      Disable caching of typechecking

Printing and debugging
~~~~~~~~~~~~~~~~~~~~~~

:samp:`--show-implicit`
      Show implicit arguments when printing

:samp:`--show-irrelevant`
      Show irrelevant arguments when printing

:samp:`--no-unicode`
      Don't use unicode characters to print terms

:samp:`--verbose={N} -v={N}`
      Set verbosity level to :samp:`{N}`

Copatterns and projections
~~~~~~~~~~~~~~~~~~~~~~~~~~

:samp:`--copatterns`
      Enable definitions by copattern matching
      (default; see :ref:`copatterns`)

:samp:`--no-copatterns`
      Disable definitions by copattern matching

:samp:`--postfix-projections`
      Make postfix projection notation the
      default

Experimental features
~~~~~~~~~~~~~~~~~~~~~

:samp:`--injective-type-constructors`
      Enable injective type
      constructors (makes Agda anti-classical and possibly
      inconsistent)

:samp:`--experimental-irrelevance`
      Enable potentially unsound
      irrelevance features (irrelevant levels, irrelevant data
      matching) (see :ref:`irrelevance`)

:samp:`--rewriting`
      Enable declaration and use of REWRITE rules (see
      :ref:`rewriting`)

:samp:`--cubical`
      Enable cubical features. Turns on ``--without-K`` (see :ref:`cubical`)

Errors and warnings
~~~~~~~~~~~~~~~~~~~

:samp:`--allow-unsolved-metas`
      Succeed and create interface file
      regardless of unsolved meta variables (see :ref:`metavariables`)

:samp:`--allow-incomplete-matches`
      Succeed and create interface file
      regardless of incomplete pattern-matching definitions

:samp:`--no-positivity-check`
      Do not warn about not strictly positive
      data types (see :ref:`positivity-checking`)

:samp:`--no-termination-check`
      Do not warn about possibly
      nonterminating code (see :ref:`termination-checking`)

:samp:`--warning={GROUP|FLAG} -W {GROUP|FLAG}`
      Set warning group or flag (see :ref:`warnings`)

Pattern matching and equality
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

:samp:`--without-K`
      Disables definitions using Streicher’s K axiom
      (see :ref:`without-K`)

:samp:`--with-K`
      Overrides a global ``--without-K`` in a file (see
      :ref:`without-K`)

:samp:`--no-pattern-matching`
      Disable pattern matching completely

:samp:`--exact-split`
      Require all clauses in a definition to hold as
      definitional equalities unless marked ``CATCHALL`` (see
      :ref:`case-trees`)

:samp:`--no-exact-split`
      Do not require all clauses in a definition to
      hold as definitional equalities (default)

:samp:`--no-eta-equality`
      Default records to no-eta-equality (see
      :ref:`eta-expansion`)

Search depth and instances
~~~~~~~~~~~~~~~~~~~~~~~~~~

:samp:`--termination-depth={N}`
      Allow termination checker to count
      decrease/increase upto :samp:`{N}` (default: 1; see
      :ref:`termination-checking`)

:samp:`--instance-search-depth={N}`
      Set instance search depth to
      :samp:`{N}` (default: 500; see :ref:`instance-arguments`)

:samp:`--inversion-max-depth={N}`
      Set maximum depth for pattern match inversion to :samp:`{N}` (default:
      50). Should only be needed in pathological cases.

:samp:`--no-overlapping-instances`
      Don't consider recursive instance arguments during pruning of
      instance candidates (default)

:samp:`--overlapping-instances`
      Consider recursive instance arguments during pruning of instance
      candidates


Other features
~~~~~~~~~~~~~~

:samp:`--safe`
      Disable postulates, unsafe ``OPTION`` pragmas and
      ``primTrustMe``. Turns off ``--sized-types`` and ``--guardedness`` (at most one can be turned back on again) (see :ref:`safe-agda`)

:samp:`--type-in-type`
      Ignore universe levels (this makes Agda
      inconsistent; see :ref:`universe-levels`)

:samp:`--omega-in-omega`
      Enable typing rule `Setω : Setω` (this makes
      Agda inconsistent).

:samp:`--sized-types`
      Enable sized types (default, inconsistent with constructor-based
      guarded corecursion; see :ref:`sized-types`). Turned off by ``--safe``
      (but can be turned on again, as long as not also ``--guardedness`` is on).

:samp:`--no-sized-types`
      Disable sized types (see :ref:`sized-types`)

:samp:`--guardedness`
      Enable constructor-based guarded corecursion (default, inconsistent
      with sized types; see :ref:`coinduction`). Turned off by ``--safe``
      (but can be turned on again, as long as not also ``--sized-types`` is on).

:samp:`--no-guardedness`
      Disable constructor-based guarded corecursion (see :ref:`coinduction`)

:samp:`--universe-polymorphism`
      Enable universe polymorphism (default;
      see :ref:`universe-levels`)

:samp:`--no-universe-polymorphism`
      Disable universe polymorphism (see
      :ref:`universe-levels`)

:samp:`--no-irrelevant-projections`
      Disable projection of irrelevant
      record fields (see :ref:`irrelevance`)

:samp:`--no-auto-inline`
      Disable automatic compile-time inlining.
      Only definitions marked INLINE will be inlined.

:samp:`--no-print-pattern-synonyms`
      Always expand :ref:`pattern-synonyms` during printing. With this option
      enabled you can use pattern synonyms freely, but Agda will not use any
      pattern synonyms when printing goal types or error messages, or when generating
      patterns for case splits.

:samp:`--double-check`
      Enable double-checking of all terms using the internal typechecker

:samp:`--no-syntactic-equality`
      Disable the syntactic equality shortcut in the conversion checker

:samp:`--no-fast-reduce`
      Disable reduction using the Agda Abstract Machine


.. _warnings:

Warnings
~~~~~~~~

The ``-W`` or ``--warning`` option can be used to disable or enable
different warnings. The flag ``-W error`` (or ``--warning=error``) can
be used to turn all warnings into errors, while ``-W noerror`` turns
this off again.

A group of warnings can be enabled by ``-W {group}``, where
:samp:`group` is one of the following:

:samp:`all`
      All of the existing warnings
:samp:`warn`
      Default warning level
:samp:`ignore`
      Ignore all warnings

Individual warnings can be turned on and off by ``-W {Name}`` and ``-W
{noName}`` respectively. The flags available are:

:samp:`AbsurdPatternRequiresNoRHS`
      RHS given despite an absurd pattern in the LHS.
:samp:`CantGeneralizeOverSorts`
      Attempt to generalize over sort metas in 'variable' declaration.
:samp:`CoverageIssue`
      Failed coverage checks.
:samp:`CoverageNoExactSplit`
      Failed exact split checks.
:samp:`DeprecationWarning`
      Feature deprecation.
:samp:`EmptyAbstract`
      Empty ``abstract`` blocks.
:samp:`EmptyInstance`
      Empty ``instance`` blocks.
:samp:`EmptyMacro`
      Empty ``macro`` blocks.
:samp:`EmptyMutual`
      Empty ``mutual`` blocks.
:samp:`EmptyPostulate`
      Empty ``postulate`` blocks.
:samp:`EmptyPrimitive`
      Empty ``primitive`` blocks.
:samp:`EmptyPrivate`
      Empty ``private`` blocks.
:samp:`EmptyRewritePragma`
      Empty ``REWRITE`` pragmas.
:samp:`IllformedAsClause`
      Illformed ``as``-clauses in ``import`` statements.
:samp:`InstanceNoOutputTypeName`
      Instance arguments whose type does not end in a named or variable type are never considered by instance search.
:samp:`InstanceArgWithExplicitArg`
      Instance arguments with explicit arguments are never considered by instance search.
:samp:`InstanceWithExplicitArg`
      Instance declarations with explicit arguments are never considered by instance search.
:samp:`InvalidCatchallPragma`
      ``CATCHALL`` pragmas before a non-function clause.
:samp:`InvalidNoPositivityCheckPragma`
      No positivity checking pragmas before non-`data``, ``record`` or ``mutual`` blocks.
:samp:`InvalidTerminationCheckPragma`
      Termination checking pragmas before non-function or ``mutual`` blocks.
:samp:`InversionDepthReached`
      Inversions of pattern-matching failed due to exhausted inversion depth.
:samp:`LibUnknownField`
      Unknown field in library file.
:samp:`MissingDefinitions`
      Names declared without an accompanying definition.
:samp:`ModuleDoesntExport`
      Names mentioned in an import statement which are not exported by the module in question.
:samp:`NotAllowedInMutual`
      Declarations not allowed in a mutual block.
:samp:`NotStrictlyPositive`
      Failed strict positivity checks.
:samp:`OldBuiltin`
      Deprecated ``BUILTIN`` pragmas.
:samp:`OverlappingTokensWarning`
      Multi-line comments spanning one or more literate text blocks.
:samp:`PolarityPragmasButNotPostulates`
      Polarity pragmas for non-postulates.
:samp:`PragmaCompiled`
      ``COMPILE`` pragmas not allowed in safe mode.
:samp:`PragmaCompileErased`
      ``COMPILE`` pragma targeting an erased symbol.
:samp:`PragmaNoTerminationCheck`
      ``NO_TERMINATION_CHECK`` pragmas are deprecated.
:samp:`RewriteMaybeNonConfluent`
      Failed confluence checks while computing overlap.
:samp:`RewriteNonConfluent`
      Failed confluence checks while joining critical pairs.
:samp:`SafeFlagNonTerminating`
      ``NON_TERMINATING`` pragmas with the safe flag.
:samp:`SafeFlagNoPositivityCheck`
      ``NO_POSITIVITY_CHECK`` pragmas with the safe flag.
:samp:`SafeFlagNoUniverseCheck`
      ``NO_UNIVERSE_CHECK`` pragmas with the safe flag.
:samp:`SafeFlagPolarity`
      ``POLARITY`` pragmas with the safe flag.
:samp:`SafeFlagPostulate`
      ``postulate`` blocks with the safe flag
:samp:`SafeFlagPragma`
      Unsafe ``OPTIONS`` pragmas with the safe flag.
:samp:`SafeFlagTerminating`
      ``TERMINATING`` pragmas with the safe flag.
:samp:`SafeFlagWithoutKFlagPrimEraseEquality`
      ``primEraseEquality`` used with the safe and without-K flags.
:samp:`ShadowingInTelescope`
      Repeated variable name in telescope.
:samp:`TerminationIssue`
      Failed termination checks.
:samp:`UnknownFixityInMixfixDecl`
      Mixfix names without an associated fixity declaration.
:samp:`UnknownNamesInFixityDecl`
      Names not declared in the same scope as their syntax or fixity declaration.
:samp:`UnknownNamesInPolarityPragmas`
      Names not declared in the same scope as their polarity pragmas.
:samp:`UnreachableClauses`
      Unreachable function clauses.
:samp:`UnsolvedConstraints`
      Unsolved constraints.
:samp:`UnsolvedInteractionMetas`
      Unsolved interaction meta variables.
:samp:`UnsolvedMetaVariables`
      Unsolved meta variables.
:samp:`UselessAbstract`
      ``abstract`` blocks where they have no effect.
:samp:`UselessInline`
      ``INLINE`` pragmas where they have no effect.
:samp:`UselessInstance`
      ``instance`` blocks where they have no effect.
:samp:`UselessPrivate`
      ``private`` blocks where they have no effect.
:samp:`UselessPublic`
      ``public`` blocks where they have no effect.
:samp:`WithoutKFlagPrimEraseEquality`
      ``primEraseEquality`` used with the without-K flags.
:samp:`WrongInstanceDeclaration`
      Terms marked as eligible for instance search should end with a name.
:samp:`CoInfectiveImport`
      Importing a file not using e.g. ``--safe``  from one which does.
:samp:`InfectiveImport`
      Importing a file using e.g. ``--cubical`` into one which doesn't.

For example, the following command runs Agda with all warnings
enabled, except for warnings about empty ``abstract`` blocks:

.. code-block:: console

   agda -W all --warning=noEmptyAbstract file.agda


.. _consistency-checking-options:

Consistency checking of options used
------------------------------------

Agda checks that options used in imported modules are consistent with
each other.

An *infective* option is an option that if used in one module, must be
used in all modules that depend on this module. The following options
are infective:

* ``--cubical``
* ``--prop``

A *coinfective* option is an option that if used in one module, must
be used in all modules that this module depends on. The following
options are coinfective:

* ``--safe``
* ``--without-K``
* ``--no-universe-polymorphism``
* ``--no-sized-types``
* ``--no-guardedness``

Agda records the options used when generating an interface file. If
any of the following options differ when trying to load the interface
again, the source file is re-typechecked instead:

* ``--termination-depth``
* ``--no-unicode``
* ``--allow-unsolved-metas``
* ``--allow-incomplete-matches``
* ``--no-positivity-check``
* ``--no-termination-check``
* ``--type-in-type``
* ``--omega-in-omega``
* ``--no-sized-types``
* ``--no-guardedness``
* ``--injective-type-constructors``
* ``--prop``
* ``--no-universe-polymorphism``
* ``--irrelevant-projections``
* ``--experimental-irrelevance``
* ``--without-K``
* ``--exact-split``
* ``--no-eta-equality``
* ``--rewriting``
* ``--cubical``
* ``--overlapping-instances``
* ``--safe``
* ``--double-check``
* ``--no-syntactic-equality``
* ``--no-auto-inline``
* ``--no-fast-reduce``
* ``--instance-search-depth``
* ``--inversion-max-depth``
* ``--warning``


.. _Vim: https://www.vim.org/
.. _Dot: http://www.graphviz.org/content/dot-language
