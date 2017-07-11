project_dir := $(dir $(abspath $(lastword $(MAKEFILE_LIST))))

PRECOMMIT_HOOK					 := $(project_dir).pre-commit
PRECOMMIT_HOOK_LINK_PATH := $(project_dir).git/hooks/pre-commit

init:
	@echo Adding pre-commit hook with rubocop checks...
	@rm -f $(PRECOMMIT_HOOK_LINK_PATH)
	@ln -s $(PRECOMMIT_HOOK) $(PRECOMMIT_HOOK_LINK_PATH)
	@chmod +x $(PRECOMMIT_HOOK_LINK_PATH)
	@echo Done.
