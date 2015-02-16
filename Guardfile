def md2html(md_path, html_path)
  `pandoc #{md_path} -s -S --toc -c pandoc.css -f markdown_github -o #{html_path}`
end

def html2pdf(html_path, pdf_path)
  `wkhtmltopdf file://#{File.expand_path(html_path)} #{pdf_path}`
end

guard "shell" do
  watch(%r{.+\.(?:md|css)$}) do
    md2html("hello.md", "hello.html")
    html2pdf("hello.html", "hello.pdf")
  end
end

guard "livereload" do
  watch(%r{.+\.(?:css|html|pdf)$})
end
