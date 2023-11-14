# Prefetch File Parser

A C++ library for parsing Windows Prefetch files

## Example Usage

Here's an example of how you can use this library to parse a prefetch file and retrieve information:

```cpp
#include "prefetch_parser.hh"

int main() {
    const auto parser = prefetch_parser(R"(prefetchfile.pf)");
    if (!parser.success()) {
        return -1;
    }

    printf("Run Count: %i\n", parser.run_count());
    printf("Executed Time: %lld\n", parser.executed_time());

    printf("File Names:\n");
    for (const auto& filename : parser.get_filenames_strings())
        printf("\t%ls\n", filename.c_str());

    return 0;
}
