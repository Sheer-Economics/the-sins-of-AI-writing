MK_DIR := $(dir $(abspath $(lastword $(MAKEFILE_LIST))))
CTX    ?= $(MK_DIR)essay.md
SEL    ?= /tmp/essay_sel.txt
OUT    ?= /tmp/essay_out.md
COMMANDS := grammar debate structure copyedit flow critique
MODEL ?= sonnet

.PHONY: $(COMMANDS)
$(COMMANDS):
	@claude -p --model $(MODEL) --append-system-prompt "$$(cat '$(CTX)')" \
	  "Run the command: $@. Text: $$(cat '$(SEL)')" > '$(OUT)' 2>&1
