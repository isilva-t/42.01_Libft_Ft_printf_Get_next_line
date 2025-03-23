OUTFILE = outfile.txt
SRC_DIR = libft

out:
	@echo "Creating $(OUTFILE) with all source files (comments removed)..."
	@echo "// Project Source Code - Comments Removed" > $(OUTFILE)
	@echo "// Generated on: `date`" >> $(OUTFILE)
	@echo "" >> $(OUTFILE)
	@find $(SRC_DIR) -type f -name "*.c" | sort | while read file; do \
		echo "\n\n// ========== $$file ==========\n" >> $(OUTFILE); \
		sed -e 's|//.*$$||g' -e 's|/\*.*\*/||g' -e '/\/\*/,/\*\//d' $$file | sed '/^[[:space:]]*$$/d' >> $(OUTFILE); \
	done
	@echo "\n\nFile generation complete. Content saved to $(OUTFILE)"
	@echo "File size: `wc -l $(OUTFILE) | awk '{print $$1}'` lines"
