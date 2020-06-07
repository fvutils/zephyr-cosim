
EXAMPLE_DIR:=$(abspath $(dir $(lastword $(MAKEFILE_LIST))))
ZEPHYR_BASE := $(abspath $(EXAMPLE_DIR)/../../packages/zephyr)
SHARE_DIR := $(abspath $(EXAMPLE_DIR)/../../src/zcosim/share)
export ZEPHYR_BASE
ZEPHYR_TOOLCHAIN_VARIANT=cosim
export ZEPHYR_TOOLCHAIN_VARIANT

#		-DARCH_ROOT=$(SHARE_DIR)/zephyr \

all:
	echo "ZEPHYR_BASE=$(ZEPHYR_BASE)"
	rm -rf build
	mkdir -p build
	cd build ; cmake .. \
		-DSOC_ROOT=$(SHARE_DIR)/zephyr \
		-DARCH_ROOT=$(SHARE_DIR)/zephyr \
		-DTOOLCHAIN_ROOT=$(SHARE_DIR)/zephyr \
		-DBOARD_ROOT=$(EXAMPLE_DIR) \
		-DBOARD=test \
		-DARCH=cosim
	cd build ; make VERBOSE=1

#cmake .. -DSOC_ROOT=/project/fun/zephyr-cosim/zephyr-cosim/src/zcosim/share/zephyr -DARCH_ROOT=/project/fun/zephyr-cosim/zephyr-cosim/src/zcosim/share/zephyr -DBOARD_ROOT=/project/fun/zephyr-cosim/zephyr-cosim/ve/example -DBOARD=test_cosim -DARCH=cosim
