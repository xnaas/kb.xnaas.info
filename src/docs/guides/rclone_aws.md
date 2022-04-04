---
title: rclone – AWS S3
description: How to use rclone with AWS S3.
og_title: rclone AWS S3 Guide
---

*[AWS]: Amazon Web Services
*[S3]: Amazon Simple Storage Service

# rclone – AWS S3

!!! warning "Gather Prior Information"
    There are two pieces of info you need to gather before proceeding. For example purposes,
    we are going to use the [US 1950 Census Dataset](https://www.archives.gov/developer/1950-census).
    
    On the linked page we're able to get the bucket name `nara-1950-census` and what region
    the data is in. For cost-saving purposes, not all buckets are available in all regions.
    You *must* find out what region(s) a bucket is in to be able to access its data. For
    the 1950 Census Dataset, that is `us-east-2` only.

## How-to

1. `rclone config`
2. `n) New remote`
3. Call it whatever you want. Recommended: all lowercase, short, and no spaces.
4. `5`
5. `1`
6. `false` (or just hit ++enter++)
7. Leave empty and hit ++enter++
8. Leave empty and hit ++enter++
9. `2` (us-east-2)
10. Leave empty and hit ++enter++
11. `2` (us-east-2)
12. Leave empty and hit ++enter++
13. Repeat step 12 until asked: `Edit advanced config?`
14. `n`
15. `y`
16. `q`

To test if this is working, simply run: `rclone lsd s3useast2:nara-1950-census`
where `s3useast2` is what you named your remote in Step 3 and `nara-1950-census` is
whatever the public bucket name is (`nara-1950-census` is good enough just to
test and verify). Your output should look something like:

```
$ rclone lsd s3useast2:nara-1950-census
           0 2022-04-04 12:29:03        -1 1950-IndianCensus
           0 2022-04-04 12:29:03        -1 1950-Territories
           0 2022-04-04 12:29:03        -1 1950census
           0 2022-04-04 12:29:03        -1 1950census-descriptions
           0 2022-04-04 12:29:03        -1 1950census-maps
           0 2022-04-04 12:29:03        -1 census-maps-highres
           0 2022-04-04 12:29:03        -1 metadata
           0 2022-04-04 12:29:03        -1 test
           0 2022-04-04 12:29:03        -1 tiff
           0 2022-04-04 12:29:03        -1 zip
```
