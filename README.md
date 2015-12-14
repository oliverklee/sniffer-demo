# Sniffer demo


This is an example for a problem with the sniffs from TYPO3SniffPool.

Sniffing code with a standard that only uses Sniffs delivered by PHP_CodeSniffer itself works fine:

    vendor/bin/phpcs --standard=Configuration/PhpCodeSniffer/Standards/Demo/ Test.php

Sniffing code using a sniff from TYPO3SniffPool crashes:

    vendor/bin/phpcs --standard=Configuration/PhpCodeSniffer/Standards/Typo3Demo/ Test.php


    PHP Fatal error:  Uncaught exception 'PHP_CodeSniffer_Exception' with message 'Referenced sniff "TYPO3SniffPool.Commenting.ClassComment" does not exist' in /home/klee/src/php/sniffer-demo/vendor/squizlabs/php_codesniffer/CodeSniffer.php:1122
    Stack trace:
    #0 /home/klee/src/php/sniffer-demo/vendor/squizlabs/php_codesniffer/CodeSniffer.php(733): PHP_CodeSniffer->_expandRulesetReference(Object(SimpleXMLElement), '/home/klee/src/...', 0)
    #1 /home/klee/src/php/sniffer-demo/vendor/squizlabs/php_codesniffer/CodeSniffer.php(551): PHP_CodeSniffer->processRuleset('/home/klee/src/...')
    #2 /home/klee/src/php/sniffer-demo/vendor/squizlabs/php_codesniffer/CodeSniffer/CLI.php(835): PHP_CodeSniffer->initStandard(Array, Array)
    #3 /home/klee/src/php/sniffer-demo/vendor/squizlabs/php_codesniffer/CodeSniffer/CLI.php(95): PHP_CodeSniffer_CLI->process()
    #4 /home/klee/src/php/sniffer-demo/vendor/squizlabs/php_codesniffer/scripts/phpcs(25): PHP_CodeSniffer_CLI->runphpcs()
    #5 {main}
      thrown in /home/klee/src/php/sniffer-demo/vendor/squizlabs/php_codesniffer/CodeSniffer.php on line 1122
