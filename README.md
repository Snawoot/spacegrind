# spacegrind
Disk usage analyzer which produces output in Cachegrind format. Program scans directory and collects information about file sizes and its count. Produced output is suitable for kcachegrind and qcachegrind analyzers, which can visualize file count and space breakdown for you.

This tool can be useful when:
* you don\`t want to rerun directory scan every time when you want to see allocated space breakdown
* you want to share scan results with others
* you have big file hierachy tree but storage server has insufficient amount of RAM to aggregate disk usage breakdown

## Usage

Scan directory `/data` and save profiling output to file `cachegrind.out.spacegrind`:

```bash
./spacegrind /data > cachegrind.out.spacegrind
```

Do the same thing and compress output on the fly:

```bash
./spacegrind /data | gzip -c > cachegrind.out.spacegrind.gz
```

## Compatibility

Program output is known to be compatible with kcachegrind and qcachegrind.
