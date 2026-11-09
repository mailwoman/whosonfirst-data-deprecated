# whosonfirst-data-deprecated

This repository lists the Who's On First IDs that the `mailwoman` forks of the
[whosonfirst-data](https://github.com/whosonfirst-data) repositories no longer carry, and the ID that
replaced each one.

Who's On First never removes a record once it is minted. The upstream repositories keep every superseded and
deprecated record, and they remain the complete history. The `mailwoman` forks remove two kinds of record to
keep the clones small:

- A **superseded** record, whose `wof:superseded_by` lists the records that replaced it.
- A **deprecated** record with no successor, whose `edtf:deprecated` is set and whose `wof:superseded_by` is
  empty.

## Layout

Each removed ID has one file. Its path follows the Who's On First layout, the ID split into groups of three
digits, and the file name is the ID without an extension:

```
data/101/846/037/101846037
```

The file holds the ID of each successor, one per line, each followed by a newline:

```
101792059
```

An empty file marks an ID that was deprecated without a successor.

A successor may itself appear here when it was later superseded. Follow the chain until an ID has no file.

## Source

Each ID was read from the record that the fork's removal commit deleted: `wof:superseded_by` for a superseded
record, and `edtf:deprecated` with an empty `wof:superseded_by` for a deprecated one. The removal commits are
titled "Remove superseded records" and "Remove deprecated records without a successor" on each fork's default
branch.

## License

The IDs and their successor relationships come from Who's On First, which is published under the licenses
listed at <https://whosonfirst.org/docs/licenses/>.
