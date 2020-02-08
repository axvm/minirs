TARGET = 'x86_64-unknown-linux-gnu'
BIN = 'minirs'

task :default do
    sh 'mkdir -p binary'
    Rake::Task[:compile].invoke

    puts "finishing"
    sh "cp target/#{TARGET}/release/#{BIN} binary/"
    sh "strip binary/#{BIN}"
    
    puts "done"
end

task :compile do
    puts "compiling binary"
    sh "xargo build --target #{TARGET} --release"
end

task :clean do
    `rm -R binary`
    `ls target/`.split(' ').each do |dir|
        next if dir == 'rls'

        `rm -R target/#{dir}`
    end
end

task :setup do
    sh 'rustup toolchain install nightly'
    sh 'rustup default nightly'
    sh 'rustup component add rust-src'
    sh 'cargo install xargo'
end