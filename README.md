# prefetch-parser

Example Usage:
```c
const auto parser = prefetch_parser( R"(prefetchfile.pf)" );
if ( !parser.success( ) )
	return -1;

printf( "Run Count: %i \n", parser.run_count( ) );
printf( "Executed Time: %s \n", parser.executed_time( ).c_str( ) );

printf( "File Names: \n" );
for ( const auto& i : parser.get_filenames_strings( ) )
	printf( "\t%ls\n", i.c_str( ) );
	
return 0;
```
