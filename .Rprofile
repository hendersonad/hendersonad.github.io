if(!"pacman" %in% rownames(utils::installed.packages())){utils::install.packages("pacman")}
pacman::p_load(randquotes)
pacman::p_load(praise)

cat("\nWelcome at", date(), "\n")
cat("\n",randquote_simple(decoded = T),"\n")
cat("\nSmoke-free for",Sys.Date()-as.Date("2021-08-10"), "days! Keep at it\n")
cat("\n", praise::praise(),"\n")

.cq <- function(x, ...) {
  if (is.character(substitute(x))) {
    res <- trimws(x)
    res <- strsplit(res, "[[:space:]]+")
    if (length(res) == 1L) res <- unlist(res)
  } else {
    pr <- substitute(list(x, ...))
    pr <- vapply(pr, deparse, character(1))
    res <- pr[-1]
  }
  tmp <- capture.output(dput(res, control = "all"))
  clipr::write_clip(tmp)
  res
}

.dib <- function(x, ...) {
	writeLines(c(
		"********************************************************\n",
		x,
		"\n********************************************************"))
}
