## git-tips
> [git-tips](http://git.io/git-tips) को संग्रह, कृपया  [contributing.md](https://github.com/git-tips/tips/blob/master/contributing.md) हेर्नुहोस्, यदि तपाइँ सुझावहरू थप्न चाहानुहुन्छ भने।

[English](http://git.io/git-tips) | [中文](https://github.com/521xueweihan/git-tips) | [Русский](https://github.com/Imangazaliev/git-tips) | [한국어](https://github.com/mingrammer/git-tips) | [Tiếng Việt](https://github.com/hprobotic/git-tips) | [日本語](https://github.com/isotai/git-tips)

### __उपकरणहरू:__

* [git-tip](https://www.npmjs.com/package/git-tip) - यो एक CLI उपकरण हो जुन तपाईं तल प्रस्तुत गरिएका सुझावहरू प्रयास गर्न सक्नुहुनेछ। ([Here in Docker container](https://github.com/djoudi5/docker-git-tip))

P.S: यी सबै आदेशहरू `git version 2.7.4 (Apple Git-66)` मा परीक्षण गरिएको हो।

<!-- @doxie.inject start toc -->
<!-- Don’t remove or change the comment above – that can break automatic updates. -->
* [हरेक दिन Git का बिस आदेशहरु वा तेस्तै](#हरेक-दिन-Git-का-बिस-आदेशहरु-वा-तेस्तै)
* [Git सँग आउने उपयोगि गाइड देखाउँछ](#Git-सँग-आउने-उपयोगि-गाइड-देखाउँछ)
* [सामाग्रिद्वारा खोजि परिवर्तन](#सामाग्रिद्वारा-खोजि-परिवर्तन)
* [धक्का पछि, इतिहासबाट संवेदनशील डेटा हटाउने](#धक्का-पछि-इतिहासबाट-संवेदनशील-डेटा-हटाउने)
* [रिमोटसँग सिङ्क गर्ने, स्थानीय परिवर्तनहरू अधिलेखन गर्ने](#रिमोटसँग-सिङ्क-गर्ने-स्थानीय-परिवर्तनहरू-अधिलेखन-गर्ने)
* [प्रतिबद्धता सम्म सबै फाइलहरूको सूची](#प्रतिबद्धता-सम्म-सबै-फाइलहरूको-सूची)
* [पहिलो प्रतिबद्धता रद्द गर्ने](#पहिलो-प्रतिबद्धता-रद्द-गर्ने)
* [सबै विवादास्पद फाइलहरू प्रदर्शन गर्ने](#सबै-विवादास्पद-फाइलहरू-प्रदर्शन-गर्ने)
* [प्रतिबद्धतामा परिवर्तन गरिएका सम्पूर्ण फाइलहरूको सूची](#प्रतिबद्धतामा-परिवर्तन-गरिएका-सम्पूर्ण-फाइलहरूको-सूची)
* [अस्थायी परिवर्तनहरू अन्तिम प्रतिबद्धताको पछिबाट](#अस्थायी-परिवर्तनहरू-अन्तिम-प्रतिबद्धताको-पछिबाट)
* [परिवर्तन प्रतिबद्धताको लागि तयारी गरियेको](#परिवर्तन-प्रतिबद्धताको-लागि-तयारी-गरियेको)
* [सुचारु र अपरिचित परिवर्तनहरू दुवै हेर्न](#सुचारु-र-अपरिचित-परिवर्तनहरू-दुवै-हेर्न)
* [पहिले नै मास्टरमा मर्ज गरिएक सबै शाखाहरू सूचीबद्ध गर्न](#पहिले-नै-मास्टरमा-मर्ज-गरिएक-सबै-शाखाहरू-सूचीबद्ध-गर्न)
* [चाँडो अघिल्लो शाखामा स्विच गर्न](#चाँडो-अघिल्लो-शाखामा-स्विच-गर्न)
* [पहिले नै मास्टरसँग मर्ज गरिएको शाखाहरू हटाउन](#पहिले-नै-मास्टरसँग-मर्ज-गरिएको-शाखाहरू-हटाउन)
* [सबै शाखाहरू र तिनीहरूका माथिल्लो सूचीहरू, साथै शाखामा अन्तिम प्रतिबद्धता सूचीबद्ध गर्न](#सबै-शाखाहरू-र-तिनीहरूका-माथिल्लो-सूचीहरू-साथै-शाखामा-अन्तिम-प्रतिबद्धता-सूचीबद्ध-गर्न)
* [दूरस्थ शाखा ट्र्याक गर्न](#दूरस्थ-शाखा-ट्र्याक-गर्न)
* [स्थानीय शाखा मेटाउन](#स्थानीय-शाखा-मेटाउन)
* [रिमोटको शाखा मेटाउन](#रिमोटको-शाखा-मेटाउन)
* [स्थानीय ट्याग मेटाउन](#स्थानीय-ट्याग-मेटाउन)
* [रिमोट ट्याग हटाउन](#रिमोट-ट्याग-हटाउन)
* [स्थानीय रूपमा संशोधित फाइलहरू HEAD मा पुनर्स्थापित गर्न](#स्थानीय-रूपमा-संशोधित-फाइलहरू-HEAD-मा-पुनर्स्थापित-गर्न)
* [उल्टाउनु: विपरीत प्रतिबद्धता गरेर मूल प्रतिबद्धता रद्द गर्नुहोस्](#उल्टाउनु-विपरीत-प्रतिबद्धता-गरेर-मूल-प्रतिबद्धता-रद्द-गर्नुहोस्)
* [रिसेट: रद्द गर्न, निजी शाखा लाई सल्लाह दिन](#रिसेट-रद्द-गर्न-निजी-शाखा-लाई-सल्लाह-दिन)
* [अघिल्लो प्रतिबद्ध टिप्पणी रिवर्ड गर्न](#अघिल्लो-प्रतिबद्ध-टिप्पणी-रिवर्ड-गर्न)
* [वर्तमान शाखाको प्रतिबद्ध इतिहास हेर्न](#वर्तमान-शाखाको-प्रतिबद्ध-इतिहास-हेर्न)
* [लेखक संशोधन गर्न।](#लेखक-संशोधन-गर्न)
* [ग्लोबल कन्फिगरमा परिवर्तन गरिसके पछि लेखक रिसेट गर्न।](#ग्लोबल-कन्फिगरमा-परिवर्तन-गरिसके-पछि-लेखक-रिसेट-गर्न)
* [रिमोटको URL परिवर्तन गर्न](#रिमोटको-URL-परिवर्तन-गर्न)
* [सबै रिमोट सन्दर्भहरूको सूची प्राप्त गर्न](#सबै-रिमोट-सन्दर्भहरूको-सूची-प्राप्त-गर्न)
* [सबै स्थानीय र रिमोट शाखाहरूको सूची प्राप्त गर्न](#सबै-स्थानीय-र-रिमोट-शाखाहरूको-सूची-प्राप्त-गर्न)
* [रिमोटका शाखाहरू मात्र पाउन](#रिमोटका-शाखाहरू-मात्र-पाउन)
* [सम्पूर्ण फाइलको सट्टामा परिवर्तन गरिएको फाइलको स्टेज भागहरू मात्र](#सम्पूर्ण-फाइलको-सट्टामा-परिवर्तन-गरिएको-फाइलको-स्टेज-भागहरू-मात्र)
* [Git बाश पूर्ण प्राप्त गर्न](#Git-बाश-पूर्ण-प्राप्त-गर्न)
* [दुई हप्ता भित्र के परिवर्तन भयो?](#दुई-हप्ता-भित्र-के-परिवर्तन-भयो)
* [मालिकबाट fork पछि गरियेका सबै प्रतिबद्धहरु](#मालिकबाट-fork-पछि-गरियेका-सबै-प्रतिबद्धहरु)
* [cherry-pick प्रयोग गरेर शाखामा प्रतिबद्ध छान्न](#cherry-pick-प्रयोग-गरेर-शाखामा-प्रतिबद्ध-छान्न)
* [प्रतिबद्ध-hash समावेश भयेका शाखाहरू फेला पार्न](#प्रतिबद्ध-hash-समावेश-भयेका-शाखाहरू-फेला-पार्न)
* [Git उपनामहरु](#git-उपनामहरु)
* [बिना प्रतिबद्ध गरि हालैको ट्र्याक गरिएका फाईलहरू बचत गर्न](#बिना-प्रतिबद्ध-गरि-हालैको-ट्र्याक-गरिएका-फाईलहरू-बचत-गर्न)
* [अस्थिर परिवर्तनहरूको वर्तमान स्थिति ट्रयाक गरिएका फाइलहरूमा बचत गर्न](#अस्थिर-परिवर्तनहरूको-वर्तमान-स्थिति-ट्रयाक-गरिएका-फाइलहरूमा-बचत-गर्न)
* [अवतरण गरिएका फाइलहरू सहित वर्तमान स्थिति बचत गर्न](#अवतरण-गरिएका-फाइलहरू-सहित-वर्तमान-स्थिति-बचत-गर्न)
* [सन्देशको साथ वर्तमान स्थिति बचत गर्दै](#सन्देशको-साथ-वर्तमान-स्थिति-बचत-गर्दै)
* [सबै फाईलहरूको हालको स्थिति बचत गर्न (बेवास्ता गरियको, नचाहिने, र ट्र्याक गरिएको)](#सबै-फाईलहरूको-हालको-स्थिति-बचत-गर्न-बेवास्ता-गरियको-नचाहिने--र-ट्र्याक-गरिएको)
* [बचत गरिएका सबै stash हरूको सूची](#बचत-गरिएका-सबै-stash-हरूको-सूची)
* [Stashed सूचीबाट नहटाई stash लागू गर्न](#stashed-सूचीबाट-नहटाई-stash-लागू-गर्न)
* [अन्तिम stashed स्थिति लागु गरि stashed सूचीबाट हताउने](#अन्तिम-stashed-स्थिति-लागु-गरि-stashed-सूचीबाट-हताउने)
* [सबै संग्रहित stash हरू हटाउने](#सबै-संग्रहित-stash-हरू-हटाउने)
* [stash बाट एकल फाइल लिन](#stash-बाट-एकल-फाइल-लिन)
* [ट्रयाक गरिएका सबै फाइलहरू हेर्न](#ट्रयाक-गरिएका-सबै-फाइलहरू-हेर्न)
* [ट्रयाक नगरिएका सबै फाइलहरू हेर्न](#ट्रयाक-नगरिएका-सबै-फाइलहरू-हेर्न)
* [उपेक्षित सबै फाइलहरू हेर्न](#उपेक्षित-सबै-फाइलहरू-हेर्न)
* [भण्डारणबाट नयाँ काम गर्ने रूख सिर्जना गर्न (git 2.5)](#भण्डारणबाट-नयाँ-काम-गर्ने-रूख-सिर्जना-गर्न-git-25)
* [HEAD स्थितिबाट नयाँ काम गर्ने रूख सिर्जना गर्न](#HEAD-स्थितिबाट-नयाँ-काम-गर्ने-रूख-सिर्जना-गर्न)
* [बिना हताई अनट्र्याक फाइलहरू](#बिना-हताई-अनट्र्याक-फाइलहरू)
* [अज्ञात फाईलहरू / डाइरेक्टरी मेटाउनु अघि, dry run गरी यी फाईलहरू / डाइरेक्टरीहरूको सूची प्राप्त गर्नुहोस्](#अज्ञातफाईलहरू-डाइरेक्टरी-मेटाउनु-अघि-dry-run-गरी-यी-फाईलहरू-डाइरेक्टरीहरूको-सूची-प्राप्त-गर्नुहोस्)
* [दृढतापूर्वक अज्ञात फाइलहरू हटाउन](#दृढतापूर्वक-अज्ञात-फाइलहरू-हटाउन)
* [दृढतापूर्वक अज्ञात डाइरेक्टरी हटाउन](#दृढतापूर्वक-अज्ञात-डाइरेक्टरी-हटाउन)
* [सबै सबमोड्यूल अद्यावधिक गर्न](#सबै-सबमोड्यूल-अद्यावधिक-गर्न)
* [हालको शाखामा सबै प्रतिबद्धहरु देखाउँन जुन अझै मास्टरमा मर्ज गर्न बाकि छ](#हालको-शाखामा-सबै-प्रतिबद्धहरु-देखाउँन-जुन-अझै-मास्टरमा-मर्ज-गर्न-बाकि-छ)
* [शाखा पुन: नामाकरण गर्न](#शाखा-पुन-नामाकरण-गर्न)
* ['feature' 'master' मा पुनर्स्थापना गर्न र मास्टर मा विलय गर्न](#feature-master-मा-पुनर्स्थापना-गर्न-र-मास्टर-मा-विलय-गर्न)
* [`Master` शाखा संग्रह गर्न](#Master-शाखा-संग्रह-गर्न)
* [प्रतिबद्ध सन्देश परिमार्जन नगरी पछिल्लो प्रतिबद्धता परिमार्जन गर्न](#प्रतिबद्ध-सन्देश-परिमार्जन-नगरी-पछिल्लो-प्रतिबद्धता-परिमार्जन-गर्न)
* [रिमोटमा मेटाइएको रिमोट शाखाहरूमा प्रक्षेपण सन्दर्भहरू।](#रिमोटमा-मेटाइएको-रिमोट-शाखाहरूमा-प्रक्षेपण-सन्दर्भहरू)
* [प्रारम्भिक संशोधनको प्रतिबद्ध hash पुनः प्राप्त गर्न।](#प्रारम्भिक-संशोधनको-प्रतिबद्ध-hash-पुनः-प्राप्त-गर्न)
* [संस्करणको रुख कल्पना गर्न।](#संस्करणको-रुख-कल्पना-गर्न)
* [reflogs बाट केवल सर्वेक्षण गरिएको सिद्धान्त सहित पेटीको भिजुअल बनाउन](#reflogs-बाट-केवल-सर्वेक्षण-गरिएको-सिद्धान्त-सहित-पेटीको-भिजुअल-बनाउन)
* [Gh-pages मा git ट्रयाक गरिएको सबफोल्डरको तैनात गर्न](#Gh-pages-मा-git-ट्रयाक-गरिएको-सबफोल्डरको-तैनात-गर्न)
* [सबट्री प्रयोग गरी भण्डारमा परियोजना थप्न](#सबट्री-प्रयोग-गरी-भण्डारमा-परियोजना-थप्न)
* [Get latest changes in your repo for a linked project using subtree](#get-latest-changes-in-your-repo-for-a-linked-project-using-subtree)
* [Export a branch with history to a file.](#export-a-branch-with-history-to-a-file)
* [Import from a bundle](#import-from-a-bundle)
* [Get the name of current branch.](#get-the-name-of-current-branch)
* [Ignore one file on commit (e.g. Changelog).](#ignore-one-file-on-commit-eg-changelog)
* [Stash changes before rebasing](#stash-changes-before-rebasing)
* [Fetch pull request by ID to a local branch](#fetch-pull-request-by-id-to-a-local-branch)
* [Show the most recent tag on the current branch.](#show-the-most-recent-tag-on-the-current-branch)
* [Show inline word diff.](#show-inline-word-diff)
* [Show changes using common diff tools.](#show-changes-using-common-diff-tools)
* [Don’t consider changes for tracked file.](#dont-consider-changes-for-tracked-file)
* [Undo assume-unchanged.](#undo-assume-unchanged)
* [Clean the files from `.gitignore`.](#clean-the-files-from-gitignore)
* [Restore deleted file.](#restore-deleted-file)
* [Restore file to a specific commit-hash](#restore-file-to-a-specific-commit-hash)
* [Always rebase instead of merge on pull.](#always-rebase-instead-of-merge-on-pull)
* [List all the alias and configs.](#list-all-the-alias-and-configs)
* [Make git case sensitive.](#make-git-case-sensitive)
* [Add custom editors.](#add-custom-editors)
* [Auto correct typos.](#auto-correct-typos)
* [Check if the change was a part of a release.](#check-if-the-change-was-a-part-of-a-release)
* [Dry run. (any command that supports dry-run flag should do.)](#dry-run-any-command-that-supports-dry-run-flag-should-do)
* [Marks your commit as a fix of a previous commit.](#marks-your-commit-as-a-fix-of-a-previous-commit)
* [Squash fixup commits normal commits.](#squash-fixup-commits-normal-commits)
* [Skip staging area during commit.](#skip-staging-area-during-commit)
* [Interactive staging.](#interactive-staging)
* [List ignored files.](#list-ignored-files)
* [Status of ignored files.](#status-of-ignored-files)
* [Commits in Branch1 that are not in Branch2](#commits-in-branch1-that-are-not-in-branch2)
* [List n last commits](#list-n-last-commits)
* [Reuse recorded resolution, record and reuse previous conflicts resolutions.](#reuse-recorded-resolution-record-and-reuse-previous-conflicts-resolutions)
* [Open all conflicted files in an editor.](#open-all-conflicted-files-in-an-editor)
* [Count unpacked number of objects and their disk consumption.](#count-unpacked-number-of-objects-and-their-disk-consumption)
* [Prune all unreachable objects from the object database.](#prune-all-unreachable-objects-from-the-object-database)
* [Instantly browse your working repository in gitweb.](#instantly-browse-your-working-repository-in-gitweb)
* [View the GPG signatures in the commit log](#view-the-gpg-signatures-in-the-commit-log)
* [Remove entry in the global config.](#remove-entry-in-the-global-config)
* [Checkout a new branch without any history](#checkout-a-new-branch-without-any-history)
* [Extract file from another branch.](#extract-file-from-another-branch)
* [List only the root and merge commits.](#list-only-the-root-and-merge-commits)
* [Change previous two commits with an interactive rebase.](#change-previous-two-commits-with-an-interactive-rebase)
* [List all branch is WIP](#list-all-branch-is-wip)
* [Find guilty with binary search](#find-guilty-with-binary-search)
* [Bypass pre-commit and commit-msg githooks](#bypass-pre-commit-and-commit-msg-githooks)
* [List commits and changes to a specific file (even through renaming)](#list-commits-and-changes-to-a-specific-file-even-through-renaming)
* [Clone a single branch](#clone-a-single-branch)
* [Create and switch new branch](#create-and-switch-new-branch)
* [Ignore file mode changes on commits](#ignore-file-mode-changes-on-commits)
* [Turn off git colored terminal output](#turn-off-git-colored-terminal-output)
* [Specific color settings](#specific-color-settings)
* [Show all local branches ordered by recent commits](#show-all-local-branches-ordered-by-recent-commits)
* [Find lines matching the pattern (regex or string) in tracked files](#find-lines-matching-the-pattern-regex-or-string-in-tracked-files)
* [Clone a shallow copy of a repository](#clone-a-shallow-copy-of-a-repository)
* [Search Commit log across all branches for given text](#search-commit-log-across-all-branches-for-given-text)
* [Get first commit in a branch (from master)](#get-first-commit-in-a-branch-from-master)
* [Unstaging Staged file](#unstaging-staged-file)
* [Force push to Remote Repository](#force-push-to-remote-repository)
* [Adding Remote name](#adding-remote-name)
* [Show the author, time and last revision made to each line of a given file](#show-the-author-time-and-last-revision-made-to-each-line-of-a-given-file)
* [Group commits by authors and title](#group-commits-by-authors-and-title)
* [Forced push but still ensure you don't overwrite other's work](#forced-push-but-still-ensure-you-dont-overwrite-others-work)
* [Show how many lines does an author contribute](#show-how-many-lines-does-an-author-contribute)
* [Revert: Reverting an entire merge](#revert-reverting-an-entire-merge)
* [Number of commits in a branch](#number-of-commits-in-a-branch)
* [Alias: git undo](#alias-git-undo)
* [Add object notes](#add-object-notes)
* [Show all the git-notes](#show-all-the-git-notes)
* [Apply commit from another repository](#apply-commit-from-another-repository)
* [Specific fetch reference](#specific-fetch-reference)
* [Find common ancestor of two branches](#find-common-ancestor-of-two-branches)
* [List unpushed git commits](#list-unpushed-git-commits)
* [Add everything, but whitespace changes](#add-everything-but-whitespace-changes)
* [Edit [local/global] git config](#edit-localglobal-git-config)
* [blame on certain range](#blame-on-certain-range)
* [Show a Git logical variable.](#show-a-git-logical-variable)
* [Preformatted patch file.](#preformatted-patch-file)
* [Get the repo name.](#get-the-repo-name)
* [logs between date range](#logs-between-date-range)
* [Exclude author from logs](#exclude-author-from-logs)
* [Generates a summary of pending changes](#generates-a-summary-of-pending-changes)
* [List references in a remote repository](#list-references-in-a-remote-repository)
* [Backup untracked files.](#backup-untracked-files)
* [List all git aliases](#list-all-git-aliases)
* [Show git status short](#show-git-status-short)
* [Checkout a commit prior to a day ago](#checkout-a-commit-prior-to-a-day-ago)
* [Push a new local branch to remote repository and track](#push-a-new-local-branch-to-remote-repository-and-track)
* [Change a branch base](#change-a-branch-base)
* [Use SSH instead of HTTPs for remotes](#use-ssh-instead-of-https-for-remotes)

<!-- Don’t remove or change the comment below – that can break automatic updates. More info at <http://npm.im/doxie.inject>. -->
<!-- @doxie.inject end toc -->


<!-- @doxie.inject start -->
<!-- Don’t remove or change the comment above – that can break automatic updates. -->
## हरेक दिन Git का बिस आदेशहरु वा तेस्तै
```sh
git help everyday
```

## Git सँग आउने उपयोगि गाइड देखाउँछ
```sh
git help -g
```

## सामाग्रिद्वारा खोजि परिवर्तन
```sh
git log -S'<a term in the source>'
```

## धक्का पछि, इतिहासबाट संवेदनशील डेटा हटाउने
```sh
git filter-branch --force --index-filter 'git rm --cached --ignore-unmatch <path-to-your-file>' --prune-empty --tag-name-filter cat -- --all && git push origin --force --all
```

## रिमोटसँग सिङ्क गर्ने, स्थानीय परिवर्तनहरू अधिलेखन गर्ने
```sh
git fetch origin && git reset --hard origin/master && git clean -f -d
```

## प्रतिबद्धता सम्म सबै फाइलहरूको सूची
```sh
git ls-tree --name-only -r <commit-ish>
```

## पहिलो प्रतिबद्धता रद्द गर्ने
```sh
git update-ref -d HEAD
```

## सबै विवादास्पद फाइलहरू प्रदर्शन गर्ने
```sh
git diff --name-only --diff-filter=U
```

## प्रतिबद्धतामा परिवर्तन गरिएका सम्पूर्ण फाइलहरूको सूची
```sh
git diff-tree --no-commit-id --name-only -r <commit-ish>
```

## अस्थायी परिवर्तनहरू अन्तिम प्रतिबद्धताको पछिबाट
```sh
git diff
```

## परिवर्तन प्रतिबद्धताको लागि तयारी गरियेको
```sh
git diff --cached
```


__विकल्पहरू:__
```sh
git diff --staged
```

## सुचारु र अपरिचित परिवर्तनहरू दुवै हेर्न
```sh
git diff HEAD
```

## पहिले नै मास्टरमा मर्ज गरिएक सबै शाखाहरू सूचीबद्ध गर्न
```sh
git branch --merged master
```

## चाँडो अघिल्लो शाखामा स्विच गर्न
```sh
git checkout -
```


__विकल्पहरू:__
```sh
git checkout @{-1}
```

## पहिले नै मास्टरसँग मर्ज गरिएको शाखाहरू हटाउन
```sh
git branch --merged master | grep -v '^\*' | xargs -n 1 git branch -d
```


__विकल्पहरू:__
```sh
git branch --merged master | grep -v '^\*\|  master' | xargs -n 1 git branch -d # will not delete master if master is not checked out
```

## सबै शाखाहरू र तिनीहरूका माथिल्लो सूचीहरू, साथै शाखामा अन्तिम प्रतिबद्धता सूचीबद्ध गर्न
```sh
git branch -vv
```

## दूरस्थ शाखा ट्र्याक गर्न
```sh
git branch -u origin/mybranch
```

## स्थानीय शाखा मेटाउन
```sh
git branch -d <local_branchname>
```

## रिमोटको शाखा मेटाउन
```sh
git push origin --delete <remote_branchname>
```


__विकल्पहरू:__
```sh
git push origin :<remote_branchname>
```

## स्थानीय ट्याग मेटाउन
```sh
git tag -d <tag-name>
```

## रिमोट ट्याग हटाउन
```sh
git push origin :refs/tags/<tag-name>
```

## स्थानीय रूपमा संशोधित फाइलहरू HEAD मा पुनर्स्थापित गर्न
```sh
git checkout -- <file_name>
```

## उल्टाउनु: विपरीत प्रतिबद्धता गरेर मूल प्रतिबद्धता रद्द गर्नुहोस्
```sh
git revert <commit-ish>
```

## रिसेट: रद्द गर्न, निजी शाखा लाई सल्लाह दिन
```sh
git reset <commit-ish>
```

## अघिल्लो प्रतिबद्ध टिप्पणी रिवर्ड गर्न
```sh
git commit -v --amend
```

## वर्तमान शाखाको प्रतिबद्ध इतिहास हेर्न
```sh
git cherry -v master
```

## लेखक संशोधन गर्न।
```sh
git commit --amend --author='Author Name <email@address.com>'
```

## ग्लोबल कन्फिगरमा परिवर्तन गरिसके पछि लेखक रिसेट गर्न।
```sh
git commit --amend --reset-author --no-edit
```

## रिमोटको URL परिवर्तन गर्न
```sh
git remote set-url origin <URL>
```

## सबै रिमोट सन्दर्भहरूको सूची प्राप्त गर्न
```sh
git remote
```


__विकल्पहरू:__
```sh
git remote show
```

## सबै स्थानीय र रिमोट शाखाहरूको सूची प्राप्त गर्न
```sh
git branch -a
```

## रिमोटका शाखाहरू मात्र पाउन
```sh
git branch -r
```

## सम्पूर्ण फाइलको सट्टामा परिवर्तन गरिएको फाइलको स्टेज भागहरू मात्र
```sh
git add -p
```

## Git बाश पूर्ण प्राप्त गर्न
```sh
curl -L http://git.io/vfhol > ~/.git-completion.bash && echo '[ -f ~/.git-completion.bash ] && . ~/.git-completion.bash' >> ~/.bashrc
```

## दुई हप्ता भित्र के परिवर्तन भयो?
```sh
git log --no-merges --raw --since='2 weeks ago'
```


__विकल्पहरू:__
```sh
git whatchanged --since='2 weeks ago'
```

## मालिकबाट fork पछि गरियेका सबै प्रतिबद्धहरु
```sh
git log --no-merges --stat --reverse master..
```

## cherry-pick प्रयोग गरेर शाखामा प्रतिबद्ध छान्न
```sh
git checkout <branch-name> && git cherry-pick <commit-ish>
```

## प्रतिबद्ध-hash समावेश भयेका शाखाहरू फेला पार्न
```sh
git branch -a --contains <commit-ish>
```


__विकल्पहरू:__
```sh
git branch --contains <commit-ish>
```

## Git उपनामहरु
```sh
git config --global alias.<handle> <command> 
git config --global alias.st status
```

## बिना प्रतिबद्ध गरि हालैको ट्र्याक गरिएका फाईलहरू बचत गर्न
```sh
git stash
```


__विकल्पहरू:__
```sh
git stash save
```

## अस्थिर परिवर्तनहरूको वर्तमान स्थिति ट्रयाक गरिएका फाइलहरूमा बचत गर्न
```sh
git stash -k
```


__विकल्पहरू:__
```sh
git stash --keep-index
```


```sh
git stash save --keep-index
```

## अवतरण गरिएका फाइलहरू सहित वर्तमान स्थिति बचत गर्न
```sh
git stash -u
```


__विकल्पहरू:__
```sh
git stash save -u
```


```sh
git stash save --include-untracked
```

## सन्देशको साथ वर्तमान स्थिति बचत गर्दै
```sh
git stash save <message>
```

## सबै फाईलहरूको हालको स्थिति बचत गर्न (बेवास्ता गरियको, नचाहिने, र ट्र्याक गरिएको)
```sh
git stash -a
```


__विकल्पहरू:__
```sh
git stash --all
```


```sh
git stash save --all
```

## बचत गरिएका सबै stash हरूको सूची
```sh
git stash list
```

## Stashed सूचीबाट नहटाई stash लागू गर्न
```sh
git stash apply <stash@{n}>
```

## अन्तिम stashed स्थिति लागु गरि stashed सूचीबाट हताउने
```sh
git stash pop
```


__विकल्पहरू:__
```sh
git stash apply stash@{0} && git stash drop stash@{0}
```

## सबै संग्रहित stash हरू हटाउने
```sh
git stash clear
```


__विकल्पहरू:__
```sh
git stash drop <stash@{n}>
```

## stash बाट एकल फाइल लिन
```sh
git checkout <stash@{n}> -- <file_path>
```


__विकल्पहरू:__
```sh
git checkout stash@{0} -- <file_path>
```

## ट्रयाक गरिएका सबै फाइलहरू हेर्न
```sh
git ls-files -t
```

## ट्रयाक नगरिएका सबै फाइलहरू हेर्न
```sh
git ls-files --others
```

## उपेक्षित सबै फाइलहरू हेर्न
```sh
git ls-files --others -i --exclude-standard
```

## भण्डारणबाट नयाँ काम गर्ने रूख सिर्जना गर्न (git 2.5)
```sh
git worktree add -b <branch-name> <path> <start-point>
```

## HEAD स्थितिबाट नयाँ काम गर्ने रूख सिर्जना गर्न
```sh
git worktree add --detach <path> HEAD
```

## बिना हताई अनट्र्याक फाइलहरू
```sh
git rm --cached <file_path>
```


__विकल्पहरू:__
```sh
git rm --cached -r <directory_path>
```

## अज्ञात फाईलहरू / डाइरेक्टरी मेटाउनु अघि, dry run गरी यी फाईलहरू / डाइरेक्टरीहरूको सूची प्राप्त गर्नुहोस्
```sh
git clean -n
```

## दृढतापूर्वक अज्ञात फाइलहरू हटाउन
```sh
git clean -f
```

## दृढतापूर्वक अज्ञात डाइरेक्टरी हटाउन
```sh
git clean -f -d
```

## सबै सबमोड्यूल अद्यावधिक गर्न
```sh
git submodule foreach git pull
```


__विकल्पहरू:__
```sh
git submodule update --init --recursive
```


```sh
git submodule update --remote
```

## हालको शाखामा सबै प्रतिबद्धहरु देखाउँन जुन अझै मास्टरमा मर्ज गर्न बाकि छ
```sh
git cherry -v master
```


__विकल्पहरू:__
```sh
git cherry -v master <branch-to-be-merged>
```

## शाखा पुन: नामाकरण गर्न
```sh
git branch -m <new-branch-name>
```


__विकल्पहरू:__
```sh
git branch -m [<old-branch-name>] <new-branch-name>
```

## 'feature' 'master' मा पुनर्स्थापना गर्न र मास्टर मा विलय गर्न
```sh
git rebase master feature && git checkout master && git merge -
```

## `Master` शाखा संग्रह गर्न
```sh
git archive master --format=zip --output=master.zip
```

## प्रतिबद्ध सन्देश परिमार्जन नगरी पछिल्लो प्रतिबद्धता परिमार्जन गर्न
```sh
git add --all && git commit --amend --no-edit
```

## रिमोटमा मेटाइएको रिमोट शाखाहरूमा प्रक्षेपण सन्दर्भहरू।
```sh
git fetch -p
```


__विकल्पहरू:__
```sh
git remote prune origin
```

## प्रारम्भिक संशोधनको प्रतिबद्ध hash पुनः प्राप्त गर्न।
```sh
 git rev-list --reverse HEAD | head -1
```


__विकल्पहरू:__
```sh
git rev-list --max-parents=0 HEAD
```


```sh
git log --pretty=oneline | tail -1 | cut -c 1-40
```


```sh
git log --pretty=oneline --reverse | head -1 | cut -c 1-40
```

## संस्करणको रुख कल्पना गर्न।
```sh
git log --pretty=oneline --graph --decorate --all
```


__विकल्पहरू:__
```sh
gitk --all
```


```sh
git log --graph --pretty=format:'%C(auto) %h | %s | %an | %ar%d'
```

## reflogs बाट केवल सर्वेक्षण गरिएको सिद्धान्त सहित पेटीको भिजुअल बनाउन
```sh
git log --graph --decorate --oneline $(git rev-list --walk-reflogs --all)
```

## Gh-pages मा git ट्रयाक गरिएको सबफोल्डरको तैनात गर्न
```sh
git subtree push --prefix subfolder_name origin gh-pages
```

## सबट्री प्रयोग गरी भण्डारमा परियोजना थप्न
```sh
git subtree add --prefix=<directory_name>/<project_name> --squash git@github.com:<username>/<project_name>.git master
```

## Get latest changes in your repo for a linked project using subtree
```sh
git subtree pull --prefix=<directory_name>/<project_name> --squash git@github.com:<username>/<project_name>.git master
```

## Export a branch with history to a file.
```sh
git bundle create <file> <branch-name>
```

## Import from a bundle
```sh
git clone repo.bundle <repo-dir> -b <branch-name>
```

## Get the name of current branch.
```sh
git rev-parse --abbrev-ref HEAD
```

## Ignore one file on commit (e.g. Changelog).
```sh
git update-index --assume-unchanged Changelog; git commit -a; git update-index --no-assume-unchanged Changelog
```

## Stash changes before rebasing
```sh
git rebase --autostash
```

## Fetch pull request by ID to a local branch
```sh
git fetch origin pull/<id>/head:<branch-name>
```


__विकल्पहरू:__
```sh
git pull origin pull/<id>/head:<branch-name>
```

## Show the most recent tag on the current branch.
```sh
git describe --tags --abbrev=0
```

## Show inline word diff.
```sh
git diff --word-diff
```

## Show changes using common diff tools.
```sh
git difftool [-t <tool>] <commit1> <commit2> <path>
```

## Don’t consider changes for tracked file.
```sh
git update-index --assume-unchanged <file_name>
```

## Undo assume-unchanged.
```sh
git update-index --no-assume-unchanged <file_name>
```

## Clean the files from `.gitignore`.
```sh
git clean -X -f
```

## Restore deleted file.
```sh
git checkout <deleting_commit>^ -- <file_path>
```

## Restore file to a specific commit-hash
```sh
git checkout <commit-ish> -- <file_path>
```

## Always rebase instead of merge on pull.
```sh
git config --global pull.rebase true
```


__विकल्पहरू:__
```sh
#git < 1.7.9
git config --global branch.autosetuprebase always
```

## List all the alias and configs.
```sh
git config --list
```

## Make git case sensitive.
```sh
git config --global core.ignorecase false
```

## Add custom editors.
```sh
git config --global core.editor '$EDITOR'
```

## Auto correct typos.
```sh
git config --global help.autocorrect 1
```

## Check if the change was a part of a release.
```sh
git name-rev --name-only <SHA-1>
```

## Dry run. (any command that supports dry-run flag should do.)
```sh
git clean -fd --dry-run
```

## Marks your commit as a fix of a previous commit.
```sh
git commit --fixup <SHA-1>
```

## Squash fixup commits normal commits.
```sh
git rebase -i --autosquash
```

## Skip staging area during commit.
```sh
git commit --only <file_path>
```

## Interactive staging.
```sh
git add -i
```

## List ignored files.
```sh
git check-ignore *
```

## Status of ignored files.
```sh
git status --ignored
```

## Commits in Branch1 that are not in Branch2
```sh
git log Branch1 ^Branch2
```

## List n last commits
```sh
git log -<n>
```


__विकल्पहरू:__
```sh
git log -n <n>
```

## Reuse recorded resolution, record and reuse previous conflicts resolutions.
```sh
git config --global rerere.enabled 1
```

## Open all conflicted files in an editor.
```sh
git diff --name-only | uniq | xargs $EDITOR
```

## Count unpacked number of objects and their disk consumption.
```sh
git count-objects --human-readable
```

## Prune all unreachable objects from the object database.
```sh
git gc --prune=now --aggressive
```

## Instantly browse your working repository in gitweb.
```sh
git instaweb [--local] [--httpd=<httpd>] [--port=<port>] [--browser=<browser>]
```

## View the GPG signatures in the commit log
```sh
git log --show-signature
```

## Remove entry in the global config.
```sh
git config --global --unset <entry-name>
```

## Checkout a new branch without any history
```sh
git checkout --orphan <branch_name>
```

## Extract file from another branch.
```sh
git show <branch_name>:<file_name>
```

## List only the root and merge commits.
```sh
git log --first-parent
```

## Change previous two commits with an interactive rebase.
```sh
git rebase --interactive HEAD~2
```

## List all branch is WIP
```sh
git checkout master && git branch --no-merged
```

## Find guilty with binary search
```sh
git bisect start                    # Search start 
git bisect bad                      # Set point to bad commit 
git bisect good v2.6.13-rc2         # Set point to good commit|tag 
git bisect bad                      # Say current state is bad 
git bisect good                     # Say current state is good 
git bisect reset                    # Finish search 

```

## Bypass pre-commit and commit-msg githooks
```sh
git commit --no-verify
```

## List commits and changes to a specific file (even through renaming)
```sh
git log --follow -p -- <file_path>
```

## Clone a single branch
```sh
git clone -b <branch-name> --single-branch https://github.com/user/repo.git
```

## Create and switch new branch
```sh
git checkout -b <branch-name>
```


__विकल्पहरू:__
```sh
git branch <branch-name> && git checkout <branch-name>
```

## Ignore file mode changes on commits
```sh
git config core.fileMode false
```

## Turn off git colored terminal output
```sh
git config --global color.ui false
```

## Specific color settings
```sh
git config --global <specific command e.g branch, diff> <true, false or always>
```

## Show all local branches ordered by recent commits
```sh
git for-each-ref --sort=-committerdate --format='%(refname:short)' refs/heads/
```

## Find lines matching the pattern (regex or string) in tracked files
```sh
git grep --heading --line-number 'foo bar'
```

## Clone a shallow copy of a repository
```sh
git clone https://github.com/user/repo.git --depth 1
```

## Search Commit log across all branches for given text
```sh
git log --all --grep='<given-text>'
```

## Get first commit in a branch (from master)
```sh
git log --oneline master..<branch-name> | tail -1
```


__विकल्पहरू:__
```sh
git log --reverse master..<branch-name> | head -6
```

## Unstaging Staged file
```sh
git reset HEAD <file-name>
```

## Force push to Remote Repository
```sh
git push -f <remote-name> <branch-name>
```

## Adding Remote name
```sh
git remote add <remote-nickname> <remote-url>
```

## Show the author, time and last revision made to each line of a given file
```sh
git blame <file-name>
```

## Group commits by authors and title
```sh
git shortlog
```

## Forced push but still ensure you don't overwrite other's work
```sh
git push --force-with-lease <remote-name> <branch-name>
```

## Show how many lines does an author contribute
```sh
git log --author='_Your_Name_Here_' --pretty=tformat: --numstat | gawk '{ add += <!-- @doxie.inject start -->; subs += <!-- @doxie.inject end -->; loc += <!-- @doxie.inject start --> - <!-- @doxie.inject end --> } END { printf "added lines: %s removed lines: %s total lines: %s
", add, subs, loc }' -
```


__विकल्पहरू:__
```sh
git log --author='_Your_Name_Here_' --pretty=tformat: --numstat | awk '{ add += <!-- @doxie.inject start -->; subs += <!-- @doxie.inject end -->; loc += <!-- @doxie.inject start --> - <!-- @doxie.inject end --> } END { printf "added lines: %s, removed lines: %s, total lines: %s
", add, subs, loc }' - # on Mac OSX
```

## Revert: Reverting an entire merge
```sh
git revert -m 1 <commit-ish>
```

## Number of commits in a branch
```sh
git rev-list --count <branch-name>
```

## Alias: git undo
```sh
git config --global alias.undo '!f() { git reset --hard $(git rev-parse --abbrev-ref HEAD)@{${1-1}}; }; f'
```

## Add object notes
```sh
git notes add -m 'Note on the previous commit....'
```

## Show all the git-notes
```sh
git log --show-notes='*'
```

## Apply commit from another repository
```sh
git --git-dir=<source-dir>/.git format-patch -k -1 --stdout <SHA1> | git am -3 -k
```

## Specific fetch reference
```sh
git fetch origin master:refs/remotes/origin/mymaster
```

## Find common ancestor of two branches
```sh
git merge-base <branch-name> <other-branch-name>
```

## List unpushed git commits
```sh
git log --branches --not --remotes
```


__विकल्पहरू:__
```sh
git log @{u}..
```


```sh
git cherry -v
```

## Add everything, but whitespace changes
```sh
git diff --ignore-all-space | git apply --cached
```

## Edit [local/global] git config
```sh
git config [--global] --edit
```

## blame on certain range
```sh
git blame -L <start>,<end>
```

## Show a Git logical variable.
```sh
git var -l | <variable>
```

## Preformatted patch file.
```sh
git format-patch -M upstream..topic
```

## Get the repo name.
```sh
git rev-parse --show-toplevel
```

## logs between date range
```sh
git log --since='FEB 1 2017' --until='FEB 14 2017'
```

## Exclude author from logs
```sh
git log --perl-regexp --author='^((?!excluded-author-regex).*)

```

## Generates a summary of pending changes
```sh
git request-pull v1.0 https://git.ko.xz/project master:for-linus
```

## List references in a remote repository
```sh
git ls-remote git://git.kernel.org/pub/scm/git/git.git
```

## Backup untracked files.
```sh
git ls-files --others -i --exclude-standard | xargs zip untracked.zip
```

## List all git aliases
```sh
git config -l | grep alias | sed 's/^alias\.//g'
```


__विकल्पहरू:__
```sh
git config -l | grep alias | cut -d '.' -f 2
```

## Show git status short
```sh
git status --short --branch
```

## Checkout a commit prior to a day ago
```sh
git checkout master@{yesterday}
```

## Push a new local branch to remote repository and track
```sh
git push -u origin <branch_name>
```

## Change a branch base
```sh
git rebase --onto <new_base> <old_base>
```

## Use SSH instead of HTTPs for remotes
```sh
git config --global url.'git@github.com:'.insteadOf 'https://github.com/'
```

<!-- Don’t remove or change the comment below – that can break automatic updates. More info at <http://npm.im/doxie.inject>. -->
<!-- @doxie.inject end -->
