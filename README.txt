--- helpful commands
kill -9 `pgrep -f "[p]ants"`
kill -9 `pgrep -f "[s]cala-compiler"`
rm -rf ~/.cache/pants/
rm -rf .pids

--- file figest error
$ ./pants generate-lockfiles && ./pants check ::
09:50:58.26 [INFO] Wrote lockfile for the resolve `jvm-default` to 3rdparty/jvm/default.lock
09:50:58.81 [ERROR] 1 Exception encountered:

  CoursierError: Coursier fetch for 'Coordinate(group='com.lihaoyi', artifact='upickle-core_2.13', version='1.5.0-1-fc17a6', packaging='jar', classifier=None, strict=True)' succeeded, but fetched artifact FileDigest('b44c8f167838c903de699bf492df571b189a5320432a2185b6ae29023905c446', 169726) did not match the expected artifact: FileDigest('89cdb5bb39d041cf2a0e2ddd3370644adb8966d2e1fed9848a0284f78ece37b3', 184796).


$ sudo grep -r ~ -e '8442ed7ee4202b43abcfc5f84dc36c5a52562fcfe061535c47e1141f42ad7a66'
Binary file /Users/abugov/.cache/pants/lmdb_store/files/9/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/files/0/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/files/7/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/files/6/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/files/1/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/files/8/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/files/f/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/files/d/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/files/4/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/files/e/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/files/b/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/files/2/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/files/5/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/directories/9/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/directories/7/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/directories/6/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/directories/8/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/directories/f/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/directories/c/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/directories/d/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/directories/3/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/directories/b/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/directories/2/data.mdb matches
Binary file /Users/abugov/.cache/pants/lmdb_store/directories/5/data.mdb matches

$ find ~ -name upickle-core_2.13
/Users/abugov/Library/Caches/Coursier/v1/https/repo1.maven.org/maven2/com/lihaoyi/upickle-core_2.13
/Users/abugov/.cache/pants/named_caches/coursier/82ce2b8f4bc8f448df4f6ed5355885af1faeecda677ab193fad51e95d47d1677/jdk/https/repo1.maven.org/maven2/com/lihaoyi/upickle-core_2.13
/Users/abugov/.cache/pants/named_caches/coursier/82ce2b8f4bc8f448df4f6ed5355885af1faeecda677ab193fad51e95d47d1677/jdk/https/maven-central.storage-download.googleapis.com/maven2/com/lihaoyi/upickle-core_2.13
/Users/abugov/.cache/pants/named_caches/coursier/a104e322b0681139a9fe7a606d9304b4d6c5cedcde94119d60dda0f0e7b4723f/jdk/https/oss.sonatype.org/content/repositories/snapshots/com/lihaoyi/upickle-core_2.13
/Users/abugov/.cache/pants/named_caches/coursier/a104e322b0681139a9fe7a606d9304b4d6c5cedcde94119d60dda0f0e7b4723f/jdk/https/repo1.maven.org/maven2/com/lihaoyi/upickle-core_2.13
/Users/abugov/.cache/pants/named_caches/coursier/a104e322b0681139a9fe7a606d9304b4d6c5cedcde94119d60dda0f0e7b4723f/jdk/https/maven-central.storage-download.googleapis.com/maven2/com/lihaoyi/upickle-core_2.13

# deleting default.lock didn't help

# this didn't help:
rm -rf \
/Users/abugov/Library/Caches/Coursier/v1/https/repo1.maven.org/maven2/com/lihaoyi \
/Users/abugov/.cache/pants/named_caches/coursier/82ce2b8f4bc8f448df4f6ed5355885af1faeecda677ab193fad51e95d47d1677/jdk/https/repo1.maven.org/maven2/com/lihaoyi \
/Users/abugov/.cache/pants/named_caches/coursier/82ce2b8f4bc8f448df4f6ed5355885af1faeecda677ab193fad51e95d47d1677/jdk/https/maven-central.storage-download.googleapis.com/maven2/com/lihaoyi \
/Users/abugov/.cache/pants/named_caches/coursier/a104e322b0681139a9fe7a606d9304b4d6c5cedcde94119d60dda0f0e7b4723f/jdk/https/oss.sonatype.org/content/repositories/snapshots/com/lihaoyi \
/Users/abugov/.cache/pants/named_caches/coursier/a104e322b0681139a9fe7a606d9304b4d6c5cedcde94119d60dda0f0e7b4723f/jdk/https/repo1.maven.org/maven2/com/lihaoyi \
/Users/abugov/.cache/pants/named_caches/coursier/a104e322b0681139a9fe7a606d9304b4d6c5cedcde94119d60dda0f0e7b4723f/jdk/https/maven-central.storage-download.googleapis.com/maven2/com/lihaoyi

# kill pants server didn't help

# deleting the whole cache (including lmdb_store) didn't help: $ rm -rf /Users/abugov/.cache/pants/


--- stack overflow error
this seems to solve the problem:
JAVA_OPTS="-Xss1G" ./pants --no-pantsd check ::

JAVA_OPTS="-Xss1G" ./pants --no-pantsd generate-lockfiles
    from some reason this "has no effect", when running 'pants check' afterwards it will error "Run `./pants generate-lockfiles` to update your lockfile based on the new requirements."

